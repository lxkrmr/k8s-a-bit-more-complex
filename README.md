# Practicing my Kubernetes skills

Hello,

this is a follow along of the course **Docker and Kubernetes** by Stephen Grider.
You can find the course on Udemy:

https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/

## FYI:

### Experience with K8s using Docker Desktop on my MacBook Air M1

I am using Docker Desktop on my MacBook Air M1 to setup a local Kubernetes Cluster with some simple clicks.

Until now everything is working fine, so I can recommend to give it a try.

### Create a K8s secret for Postgres

If you want to try it yourself, then you have to create a k8s secret to store the password for postgres, like this:

    kubectl create secret generic pgpassword --from-literal PGPASSWORD=password123

### Setting up an Ingress on your local machine using Helm

To follow along with setting up the ingress, I installed helm first by using brew:

    brew install helm

Afterwards I ran the following helm command:

    helm upgrade --install ingress-nginx ingress-nginx \
        --repo https://kubernetes.github.io/ingress-nginx \
        --namespace ingress-nginx --create-namespace

### Lens > Deploying K8s Dashboard UI on your local machine

Deploying the K8s dashboard on my local machine did not work for me, here the link to the doc: 

https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/#deploying-the-dashboard-ui

When I tried to receive a token for the login with this command...

    kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"

then I got this error:

    error: error executing template "{{.data.token | base64decode}}": template: output:1:16: executing "output" at <base64decode>: invalid value; expected string    

Sadly a quick search did not helped, so I decided to skip it and use Lens instead.
It is much easier to use and you don't have to go through this pain ;)

https://k8slens.dev/
