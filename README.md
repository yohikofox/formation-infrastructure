# Formation à l'infrastructure as code

Ce dépôt ``git`` a pour but de se former aux technologies liées à l'infrastructure. La manière de fonctionner est la suivante: 

1. Une branche par thème permet de se former en s'exerçant. `git checkout [theme]/exercice`
2. Une branche par thème permet d'avoir un exemple fonctionnel de ce qui est présenté. `git checkout [theme]/solution`

## Level : `basics`

### Ce qui sera traité ici

* Apprendre les bases Kubernetes 
  * theme: `basics/kubernetes`
* Apprendre les bases de Helm 
  * theme: `basics/helm`
* Apprendre les bases de Terraform 
  * theme: `basics/terraform`


### Légende

Couleur                                                                                                                    | signification
---------------------------------------------------------------------------------------------------------------------------|-----------------
<span style="color: #000; background-color:#e8e8e8; padding: 10px 20px; border: 1px solid #000; line-height:50px;"></span> | Non déployable
<span style="color: #000; background-color:#00FF00; padding: 10px 20px; border: 1px solid #000; line-height:50px;"></span> | A déployer
<span style="color: #000; background-color:#6FA2FF; padding: 10px 20px; border: 1px solid #000; line-height:50px;"></span> | Services managés
<span style="color: #000; background-color:#a6a6a6; padding: 10px 20px; border: 1px solid #000; line-height:50px;"></span> | SI externe

### Glossaire

* [P,C,A]: action avec un `message brocker`
  * \[P\]: Produce
  * \[C\]: Consume
  * \[A\]: Acknoledge
* R/W : Lecture Ecriture
  * R: Read
  * W: Write

### Ce qui doit être déployé

```plantuml
skinparam linetype ortho

actor Utilisateur as cl
node Website as cs  #e8e8e8

node TheTribe {

  node Applications {
    node Frontend as fo #00FF00
      node Backoffice as bo {
        node Backend as be  #00FF00
        control "Background Worker" as bg #00FF00
        database db as db  #6FA2FF
      }
      queue broker as br #6FA2FF
  }
}

cl ---( cs : Centre d'interactions
cs --( fo : Rendre une page ou\nune partie de page
cs <--> be : get/post/put data

be -down-|> br : [P]
bg --left-( br: [C|A]

be --( db: R
bg --|> db: W
```

### Infrastructure à mettre en place

```plantuml
actor user  as u

node Kubernetes as kube {
  port p1
  node "App Node" as app_n{
    node pods as ps {
        node frontend as p_fo
        node backend as p_be
    }
  }

  node cert_manager {
    rectangle www as tls_www
    rectangle api as tls_api
  }
  node ingress_controller as nginx {
      package ingress {
        rectangle www as in_www
        rectangle api as in_api
      }

      in_www --> tls_www
      in_api --> tls_api
  }

  in_www --> p_fo
  in_api --> p_be
}

u ----> p1
p1 ----> nginx
```