# Laravel + K8s no GCP

![enter image description here](https://i.morioh.com/e877e33449.png)

Este é um exemplo de integração e entrega continua em contêineres utilizando o K8s.

A os processos de CI/CD serão executados do Cloud Build e entregues no kubernetes do GCP. 


# Deployments

Serão implementados os seguintes deployments e seus serviços, Mysql, Redis, Nginx e APP(Laravel). 

 - **Mysql-service e Redis-service** - Utilizará de um cluster NO IP, sem acesso externo. 
 - ** Nginx  ** - Utilizará de um Cluster IP do tipo LoadBalancer expondo a aplicação na porta 80
 - ** App ** -  Utilizará de um nodePort para que seja possivel consumir a APP em qualquer porta acima da 30080 


# Como colocar para funcionar

### Dependências

 1. Conta no GCP
 2. 1 ou mais clusters do K8s criados no GCP
 3. Triggers do cloud build criadas para ouvir a branch master do repositório 

Com tudo isso em mãos, basta utilizar configurar o contexto do k8s do GCP ao seu kubectl e executar o comando. 

		   

     kubectl apply -f k8s/

   
E acompanhar a criação dos seus pods, services e tudo mais. 

[@despossivel](https://www.linkedin.com/in/despossivel/)

 