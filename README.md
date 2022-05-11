# Practicing my Kubernetes skills

Hello,

this is a follow along of the course **Docker and Kubernetes** by Stephen Grider.
You can find the course on Udemy:

https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/

JFYI:

I am using Docker Desktop on my MacBook Air M1 to setup a local Kubernetes Cluster with some simple clicks.

Until now everything is working fine, so I can recommend to give it a try.

----

If you want to try it yourself, then you have to create a k8s secret to store the password for postgres, like this:

    kubectl create secret generic pgpassword --from-literal PGPASSWORD=password123