# Proyecto Tolerante a fallas

Proyecto final de la clase de Computación tolerante a fallas 

Universidad de Guadalajara 

Departamento:  Departamento de ciencias computacionales

Nombre del maestro: López Franco Michel Emanuel

Carrera: Ingeniería en computación 

Sección: D06

Ciclo: 23B

Fecha: 4/12/2023

Ingregantes:

-Loredo Padilla Orlando Javier  217560328  

-Portillo Correa Luis Jaime   217546155

-Salcido Aviña Carlos Uriel     217560751



--Calculadora con el uso de istio y soporte para caos-- 

Nuestro programa toma como base una calculadora con sus operaciones basicas con un sistema de conversiones de diferentes sistemas, el objetivo es hacer correr una calculadora mediante la simulación de un contedor usando docker, donde que cada una de sus funciones se aloje como un micoroservicio e implementando kubernetes para ampliar la capacidad de estos. Esto contaría como lo basico ya que implementará istio para manejar la carga de trabajo del programa y caos para comprobar su tolerancia a fallas.


Nuestra calculadora contiene distintos archivos para funcionar, como se mencionó se dividieron por microservicios entonces por funcionamiento dispondremos de distintos archivos los cuales contendrán una función en específico, para esto decidimos trabajar usando JavaScript. Un ejemplo sería el siguiente archivo de JS el cual contiene la función de la conversión de temperaturas, como esta parte la estaremos trabajando desde un mismo usaremos un switch para alternar entre opción que de igual manera se reflejará en la arquitectura del programa.
![image](https://github.com/Orlando-Javier-Loredo-Padilla/Proyecto-Tolerante-a-fallas/assets/123122353/170aa849-a22f-4bfc-9f8c-3db35abbad0d)

Este proceso lo replicaremos para cada función en nuestro programa, esto será fundamental para crear nuestros microservicios. Lo siguiente será crear los archivos para que los anteriores puedan correr en contenedores, usaremos un server de express para poder hacer uso de estas funciones. Del mismo modo haremos esto para cada microservicio. 
![image](https://github.com/Orlando-Javier-Loredo-Padilla/Proyecto-Tolerante-a-fallas/assets/123122353/20fe5449-e64c-4415-b2f5-87a5448f3527)

Del mismo modo crearemos nuestros dockerfile con los cuales indicaremos los parámetros con los cuales queremos que se ejecuten nuestros contenedores, la imagen, puerto, arhivos entre otros; será uno para cada función como ya se ha estado aclarando previamente. 
![image](https://github.com/Orlando-Javier-Loredo-Padilla/Proyecto-Tolerante-a-fallas/assets/123122353/47658960-25e6-49c2-95cf-f8794240da68)


Pasaremos a hacer uso de minikube, herramienta que sirve para la implementación de kubernetes y hacer uso de sus funcionalidades, punto importante a considerar en el trabajo, al usarlo aquí podremos gestionar con facilidad nuestro cluster de kubernetes de manera local. Simularemos una situación en la cual disponemos de varios servidores en los cuales cada uno hará uso de su propio contenedor, esto por medio de maquinas virtuales de virtualbox. En la consola, al ejecutarlo, podremos ver la lista de los servicios que componen nuestro cluster. Estos servicios también contaran con un balanceo de carga para mejor funcionamiento. 

![image](https://github.com/Orlando-Javier-Loredo-Padilla/Proyecto-Tolerante-a-fallas/assets/123122353/7563ce5b-76f4-4594-ace4-c2342ee0bc30)




