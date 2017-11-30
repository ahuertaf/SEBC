# CM Monitoring Lab

Use CM to answer the following questions. For some questions, search will help you. Watch out for trick questions! (Some of these questions have been asked by customers.) Put the questions and their answers in the file enterprise/labs/0_CM_treasure_hunt.md

## What is ubertask optimization?

### Una función que nos permite ejecutar los procesos pequeños de manera secuencial 

## Where in CM is the Kerberos Security Realm value displayed?

### Ajustes->kerberos->Dominio de seguridad de Kerberos (default_realm)


## Which CDH service(s) host a property for enabling Kerberos authentication?

### Explisitamente solo ZooKeeper, YARN pero HDFS tambien lo permite

## How do you upgrade the CM agents?

###  Para poder actualizar los agentes es necesario primero actualizar el CM server y una vez actualizado después de iniciar sesion por primera vez, nos preguntará si queremos actualizar los agentes o de forma manual con los siguientes comandos.

```sh
service cloudera-scm-agent stop
yum upgrade 'cloudera-*'
service cloudera-scm-agent start
```

## Give the tsquery statement used to chart Hue's CPU utilization?

### select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME

## Name all the roles that make up the Hive service

### HUE Server, HUE Balancer y cuando está implementado kerberos Kerberos Ticket Renewer

## What steps must be completed before integrating Cloudera Manager with Kerberos?

### 1.- Tener correctamente configurado CM
### 2.- Instalar Kerberos Server en el que será nuestro servidor de Seguridad
### 3.- Instalar el cliente de Kerberos en todos nuestros nodos
### 4.- Configurar los clientes y el server para que se conecten entre si
### 5.- Crear el o los usuarios necesarios y asignarle los permisos
### 6.- Iniciar los servicios de kerberos 
### 7.- Iniciar desde el CM los pasos para la integración 

