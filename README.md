# Formation à l'infrastructure as code

Ce dépôt ``git`` a pour but de se former aux technologies liées à l'infrastructure. La manière de fonctionner est la suivante: 

1. Une branche par thème permet de se former en s'exerçant. `git checkout [theme]-exercise`
2. Une branche par thème permet d'avoir un exemple fonctionnel de ce qui est présenté. `git checkout [theme]-solution`

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

![](.asset/diagram_global.svg)

### Infrastructure à mettre en place

![](.asset/infrastructure.svg)