# otus_arch_homework_health
Домашнее задание к лекции Основы работы с Kubernetes часть 2

1. В папке с манифестами выполнить команду
kubectl apply -f .

2. В minikube вводим 
minikube ssh

3. Исполняем команду 
curl -H 'Host: arch.homework' http://127.0.0.1/otusapp/dikhnich/health

Должен быть ответ:
{"status": "ok"}

4. Если хотим делать запрос по имени хоста, исполняем в kubectl команду
kubectl get ingress

у меня ответ:
NAME            CLASS    HOSTS           ADDRESS        PORTS   AGE
hello-ingress   <none>   arch.homework   192.168.49.2   80      43m

5. В файле hosts прописываем правило
192.168.49.2 arch.homework

6. В minikube ssh делаем запрос
curl http://arch.homework/otusapp/dikhnich/health

Должен быть ответ:
{"status": "ok"}

