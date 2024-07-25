# Nginx_on_Kubernetes

As I am exploring the world of Kubernetes, I decided to experiment with a basic project where I deploy a simple Nginx web server using Minikube on Windows and access it via the service URL. Here are the steps that I followed.

## Start Minikube and apply manifests

First, since I have already installed Minikube and kubectl on my local machine, I just need to start it with the command "minikube start". 

![Screenshot (339)](https://github.com/user-attachments/assets/200fa974-2cd6-489b-98ed-6a34171b8d73)

I create my namespace, deployment and service manifests. Then I apply them, first the namespace and then the next two in the specified namespace.

![Screenshot (340)](https://github.com/user-attachments/assets/554a48e0-2807-4f15-9c44-3a93e66e08a8)
![Screenshot (342)](https://github.com/user-attachments/assets/146bcdc2-0045-4f66-ab91-ed91655d0a27)

I verify that my pod is running.

![Screenshot (343)](https://github.com/user-attachments/assets/84cb51d7-8b9f-4be4-af56-68489049642d)

## Start Minikube tunnel

In order to connect to my web server, I use Minikube tunnel. So I proceed to open a new tab in my terminal and start Minikube tunnel to route traffic to the LoadBalancer service. I keep the tab open as it will maintain the tunnel.

![Screenshot (344)](https://github.com/user-attachments/assets/2adfbe23-be5e-4961-b0f5-413c768850ce)

## Access the Nginx web server

In my main terminal tab, I enter the command "minikube service nginx-service --namespace development --url" to get the URL of the service within the namespace.

![Screenshot (345)](https://github.com/user-attachments/assets/2047defd-be0c-402e-8a19-947a08e69ccf)

I retrieve the URL and paste it to my web browser, where I successfully connect.

![Screenshot (347)](https://github.com/user-attachments/assets/5b6f8ea4-1a72-4f3d-8345-6b408289c843)

## Clean up resources

As a last step, I need to tear everything down and stop the Minikube. First I stop the Minikube tunnel from running.

![Screenshot (348)](https://github.com/user-attachments/assets/524adce6-9a53-4486-a19a-918ad08cc997)

Then I proceed to delete all the manifest files and the namespace.

![Screenshot (350)](https://github.com/user-attachments/assets/1fd28244-ebb7-44e9-8615-c456e8fb7851)

Finally I stop Minikube, since I no longer need it running.

![Screenshot (351)](https://github.com/user-attachments/assets/9cae5320-ba5d-4a69-85cd-90cdf8b39f3c)


