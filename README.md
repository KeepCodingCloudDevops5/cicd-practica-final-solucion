# cicd-practica-final-solucion

Una de las posibles soluciones para [la práctica final del módulo sobre CI/CD del bootcamp DevOps de KeepCoding](https://github.com/KeepCodingCloudDevops5/keepcoding-devops-cicd-practica-final.git)

## Requisitos en la instancia de Jenkins
 * Instancia de Jenkins con los plugins Job DSL y Docker instalados
 * Credenciales de AWS guardadas en la propia instancia de Jenkins con el ID `aws-credentials`
 * Configurado Docker como nube en Jenkins además del agente de terraform

## Activos del proyecto

 * [Proyecto de infraestructura como código](./infra) usando [terraform](https://www.terraform.io/) para el despliegue de unidades de almacenamiento en la nube
 * [Dockerfiles](./agents) correspondientes a los agentes de Jenkins necesarios
 * [Jenkinsfile](./Jenkinsfile.deploy) para ejecutar el despliegue con terraform usando Jenkins
 * [Github Actions YAML](./ghactions.yml) para ejecutar el despliegue con terraform usando Github Actions
 * [Jenkinsfile](./Jenkinsfile.check) para ejecutar chequeos periódicos de memoria utilizada por las unidades de almacenamiento
 * [DSLs](./DSLs) necesarios para crear ambos jobs de Jenkins
 * [Makefile](./Makefile) para desarrolladores/as

## Instrucciones para desarrolladores/as

Usa el [Makefile](./Makefile) proporcionado para desplegar la infraestructura en el entorno de *desarrollo* corriendo:

```bash
    make all
```

También puedes correr individualmente los pasos `clean`, `init`, `plan` o `apply`.