# Computación Cuántica


## NUTI-2023-1
	  								     Yudy Camila Fuentes Pardo
										    	cód 1000096896

# Entrega NUTI basado en computación cuántica 


Hola: 

Para esta actividad se realizaron los siguientes procesos

## Contenido: 🗂️ 

* [Instalación](#Instalacion)
* [Ejecución](#Ejecucion)
* [Análisis proceso](#proceso)

<a name="Instalacion"></a>
## Instalación 🧰
El link mediante el cual realizaremos la instalación son los siguientes:

>
> [Python](https://www.python.org/downloads/) 
>
> [Jupyter](https://jupyter.org/install) 
> 
> [Anaconda](https://www.anaconda.com/)

Finalizando la instalación ejecutaremos anaconda: 
      ![image](https://user-images.githubusercontent.com/26396833/226739760-01c637e9-a12c-4a13-b4b4-abe66be68e16.png)

Procederemos a elegir Jupyter Lab y nos inicia el laucher elegir el notebook: 
      ![image](https://user-images.githubusercontent.com/26396833/226740258-944f9782-8f8d-4975-a8f5-6786490b3f67.png)

Con  esto pasaremos a la ejecución: 

<a name="Ejecucion"></a>
## Ejecución 📍 

	1. Seguiremos las instrucciones de instalación para el funcionamiento de qiskit
	2. Instalaremos los paquetes para el funcionamiento 
	3. Realizaremos los pasos para ver la solución implementada 
	
### Instalación qiskit 
Realizamos los siguientes comandos para incluir los paquetes de quiskit: 
  * Paquete de instalación del paquete de optimización
    ```
    pip install qiskit-optimization
    ```
  * Paquete de instalación del paquete de [cplex](#cplex)
    ```
    pip install qiskit-optimization[cplex]
    ```
  * Paquete de instalación del paquete de matplotlib
    ```
    pip install matplotlib
    ```
  * En mi caso realice la instalación desde shell para probar , los resultados se veían de la siguiente manera pero en anaconda no funcionaban, por lo cual realizamos otro proceso adicional
  * Proceso realizado en shell de la instalación: ![image](https://user-images.githubusercontent.com/26396833/226746718-1d079134-c5bc-4450-adf5-0efb2c843078.png)
  * Proceso que se debe realizar en caso de fallas: ![image](https://user-images.githubusercontent.com/26396833/226747130-2e2a7e15-fa14-45ac-a3b3-17242a1b6416.png)
  * Empezamos a ejecutar las lineas de comandos: 
  * Revisamos si funciona el código:
  
  	![image](https://user-images.githubusercontent.com/26396833/226747630-58a25752-d780-40f9-a221-6956027df651.png)
  * No funciona volvemos a ejecutar el cplex: ![image](https://user-images.githubusercontent.com/26396833/226748080-32f8fd44-197a-4fc9-ab18-4bc398616fd1.png)
  * Ejecutamos cada uno de los pasos del código para ver su resultado 
  * Parte 1: 
    
    ![image](https://user-images.githubusercontent.com/26396833/226748325-f8260356-052f-4060-83cd-173714d9faf7.png)
  * Parte 2 : 
    
    ![image](https://user-images.githubusercontent.com/26396833/226748447-e51950ad-9052-4815-a187-4d9cec28dcb4.png)
  * Parte 3 : 
  
    ![image](https://user-images.githubusercontent.com/26396833/226748619-d523d13e-a014-4a12-acf8-8a7f9688893d.png)
  * Resultado : 
  
    ![image](https://user-images.githubusercontent.com/26396833/226748711-625d75e6-a87d-4feb-898e-c1e8ad1a6a56.png)


<a name="proceso"></a>
## Análisis proceso 🔎 
Como hemos podido evidenciar en todo este proceso qiskit es un conjunto de algoritmos de optimización cuántica generados de manera fácil de utilizar, los cuales se encuentran listos para ejecutarse como lo revisábamos en clase, se pueden utilizar su código, ya que es abierto a través de Qiskit.

Para poder realizar el ejercicio que en este caso tomamos que es en la optimización por medio de Qiskit, aclarando que la sección de optimización tiene varios proyectos en este caso realizamos el proceso para ver como funciona el enrutamiento de vehículos.[enlace](https://qiskit.org/documentation/optimization/tutorials/07_examples_vehicle_routing.html)

Lo que se busca con este proceso es realizar establecer las ubicaciones de los clientes, revisar y calcular las distancias, los tiempos de viaje, calcular las rutas reales esto lo realizan basado en un algoritmo híbrido alternativo en la computadora cuántica, adicional se visualizan los resultados. 

En qiskit nos realizan la explicación la aclaración mediante el modelo matemático y el modelo cuántico.

Ahora bien cómo funciona el código o que es lo que realiza, al realizar la importación de las tres librerías

### Matplotlib
Información acerca de como funciona la librería https://matplotlib.org/

Para generar gráficos de dos dimensiones, generados a partir de datos contenidos en listas o matrices en el lenguaje de programación Python

### Optimización
Acerca de: https://qiskit.org/documentation/stable/0.28/apidoc/qiskit_optimization.html


<a name="cplex"></a>
### Cplex 
Acá encontraremos documentación de https://ibmdecisionoptimization.github.io/docplex-doc/



Saludos 


### Autora  👩‍🎓 👩‍💻
  Yudy Camila Fuentes Pardo
