# Computación Cuántica


## NUTI-2023-1
	  								     Yudy Camila Fuentes Pardo
										    	cód 1000096896

# Entrega NUTI basado en computación cuántica 


Hola: 

Para esta actividad se realizaron los siguientes procesos de una automatización de enrutamiento de vehículos manejando computación cuántica, la información suministrada desde: https://qiskit.org/documentation/optimization/tutorials/07_examples_vehicle_routing.html


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
Si vamos a revisar la parte 3 de las imágenes, encontraremos la llamada del visualizador que nos entrega el gráfico para ver los resultados que genera el algoritmo.

```

    
# Visualize the solution
def visualize_solution(xc, yc, x, C, n, K, title_str):
    plt.figure()
    plt.scatter(xc, yc, s=200)
    for i in range(len(xc)):
        plt.annotate(i, (xc[i] + 0.15, yc[i]), size=16, color="r")
    plt.plot(xc[0], yc[0], "r*", ms=20)

    plt.grid()

    for ii in range(0, n**2):

        if x[ii] > 0:
            ix = ii // n
            iy = ii % n
            plt.arrow(
                xc[ix],
                yc[ix],
                xc[iy] - xc[ix],
                yc[iy] - yc[ix],
                length_includes_head=True,
                head_width=0.25,
            )

    plt.title(title_str + " cost = " + str(int(C * 100) / 100.0))
    plt.show()


if x is not None:
    visualize_solution(xc, yc, x, classical_cost, n, K, "Classical")
```

### Qiskit Optimización
Acerca de: https://qiskit.org/documentation/stable/0.28/apidoc/qiskit_optimization.html

Qiskit es un framework de código abierto para la programación cuántica que permite a los desarrolladores construir, simular y ejecutar circuitos cuánticos en computadoras cuánticas reales o simuladas. El framework proporciona una amplia gama de herramientas y bibliotecas para facilitar el trabajo con la computación cuántica, desde el diseño y la simulación de circuitos hasta la ejecución en hardware. La estructura de Qiskit está construida en torno a tres componentes principales: Terra, Aer e Ignis. Terra es la capa de abstracción más baja y se encarga de la construcción de circuitos cuánticos. Aer es la capa intermedia y proporciona herramientas para simular circuitos cuánticos en diferentes plataformas, incluyendo simulaciones de hardware y software. Ignis es la capa superior y proporciona herramientas para la caracterización, verificación y calibración de los dispositivos cuánticos. Qiskit utiliza el lenguaje de programación Python y ofrece una amplia gama de herramientas y bibliotecas para la programación cuántica. Algunas de las herramientas más importantes de Qiskit son: Circuitos cuánticos: Qiskit permite a los desarrolladores construir circuitos cuánticos utilizando una interfaz intuitiva y fácil de usar. Los circuitos se construyen a partir de compuertas cuánticas básicas, como compuertas de Hadamard, compuertas de Pauli y compuertas de CNOT. Simuladores: Qiskit ofrece varios simuladores para simular circuitos cuánticos en diferentes plataformas, como simuladores de hardware, simuladores de ruido y simuladores de software. Estos simuladores permiten a los desarrolladores simular circuitos cuánticos y analizar su comportamiento antes de ejecutarlos en hardware. Ejecución en hardware: Qiskit proporciona una plataforma para ejecutar circuitos cuánticos en hardware real, incluyendo dispositivos de IBM Quantum. Los desarrolladores pueden enviar sus circuitos a través de la nube y ejecutarlos en hardware real para obtener resultados reales. Bibliotecas de algoritmos: Qiskit también proporciona una amplia gama de bibliotecas de algoritmos cuánticos, incluyendo algoritmos de factorización de enteros, algoritmos de búsqueda, algoritmos de optimización y más. Estas bibliotecas permiten a los desarrolladores aprovechar la potencia de la computación cuántica para resolver problemas complejos. En general, Qiskit es un framework completo y poderoso para la programación cuántica que permite a los desarrolladores trabajar en todos los aspectos de la computación cuántica, desde la construcción de circuitos hasta la ejecución en hardware real. Con herramientas intuitivas y bibliotecas preconstruidas, Qiskit facilita el trabajo con la computación cuántica y permite a los desarrolladores aprovechar la potencia de esta tecnología emergente para resolver problemas complejos. 

<a name="cplex"></a>
### Cplex 
Acá encontraremos documentación de https://ibmdecisionoptimization.github.io/docplex-doc/

CPLEX es un software de optimización matemática desarrollado por IBM que proporciona soluciones precisas y rápidas para una amplia variedad de problemas de optimización. El software está diseñado para encontrar soluciones óptimas o casi óptimas para problemas de programación matemática que involucran modelos lineales, enteros y no lineales. CPLEX se utiliza en una amplia variedad de aplicaciones, incluyendo la optimización de procesos industriales, la planificación de la producción, la logística, la asignación de recursos y la gestión de carteras. En el contexto del VRP, CPLEX se utiliza para encontrar la solución óptima del problema de enrutamiento de vehículos, minimizando la distancia total recorrida por los vehículos mientras se satisfacen las restricciones del problema. CPLEX proporciona una interfaz de programación para varios lenguajes de programación, incluyendo Python, Java, C++ y C#. Esto permite a los programadores integrar CPLEX en sus aplicaciones de software existentes y desarrollar soluciones personalizadas para problemas de optimización específicos. El algoritmo de optimización subyacente en CPLEX se basa en técnicas de optimización lineal y de programación entera mixta. CPLEX utiliza una variedad de técnicas para resolver problemas de optimización, incluyendo métodos de corte, métodos de relajación, y heurísticas para encontrar soluciones subóptimas. Una de las principales ventajas de CPLEX es su capacidad para resolver problemas de optimización de gran tamaño y complejidad. CPLEX utiliza técnicas avanzadas de procesamiento paralelo y distribuido para acelerar la solución de problemas de optimización y aprovechar los recursos informáticos disponibles. En resumen, CPLEX es una herramienta de software de optimización de alta calidad que proporciona soluciones precisas y rápidas para una amplia variedad de problemas de optimización. En el contexto del VRP, CPLEX se utiliza para resolver el problema formulándolo como un problema de programación entera mixta, y luego encontrar la solución óptima utilizando técnicas avanzadas de optimización lineal y entera mixta. 

# Resultado 📈
Este código implementa una solución clásica al Problema de Enrutamiento de Vehículos (VRP) utilizando IBM ILOG CPLEX. El VRP es un problema de optimización combinatoria que involucra encontrar rutas óptimas para un conjunto de vehículos que comienzan y terminan en un depósito y deben visitar un conjunto de clientes. El objetivo es minimizar la distancia total recorrida por los vehículos mientras se satisfacen algunas restricciones, como una capacidad máxima para cada vehículo y el requisito de que cada cliente debe ser visitado exactamente una vez. El código define una clase Inicializador que genera una instancia aleatoria del problema, que consiste en las posiciones de los nodos (clientes y depósito) y las distancias entre ellos. También define una clase Optimizador Clásico que codifica el problema en una forma que puede ser resuelta utilizando CPLEX, un poderoso solucionador de optimización que puede encontrar soluciones exactas para muchos problemas de optimización combinatoria. La clase Optimizador Clásico define las restricciones del VRP utilizando la API de Python de CPLEX y luego resuelve el problema utilizando el solucionador incorporado de CPLEX. La clase Optimizador Clásico utiliza una formulación de programación entera mixta (MIP) para codificar el VRP. Las variables de decisión son variables binarias que indican si cada posible borde en el grafo es utilizado por los vehículos o no. La función objetivo es minimizar la distancia total recorrida por los vehículos, que es una función lineal de las variables de decisión. Las restricciones aseguran que cada cliente sea visitado exactamente una vez, que cada vehículo tenga una capacidad máxima y que las rutas formen un recorrido válido. En general, este código proporciona una solución clásica al VRP que puede encontrar soluciones exactas para pequeñas instancias del problema. Sin embargo, para instancias más grandes, el tiempo de ejecución del solucionador puede volverse prohibitivamente largo, y métodos alternativos como algoritmos heurísticos o computación cuántica pueden ser más adecuados. 

El código proporcionado es una implementación de un solucionador de problemas de optimización utilizando la computación cuántica. Específicamente, parece estar resolviendo un problema del Vendedor Ambulante (TSP) utilizando un enfoque del Algoritmo de Optimización Cuántica Aproximada (QAOA). El código comienza definiendo una clase llamada QuantumOptimizer que contiene métodos para codificar el problema en una formulación binaria utilizando Programación Cuadrática (QP), construir el problema QP y resolverlo utilizando un solucionador cuántico basado en la clase MinimumEigenOptimizer de Qiskit. El método binary_representation() codifica el problema del TSP en un problema QP, que es un problema de optimización matemático que consiste en minimizar una función objetivo cuadrática sujeta a restricciones lineales, utilizando variables binarias. El método construye una formulación QP en términos de los pesos y las interacciones entre las variables del problema, la contribución de las variables individuales y un desplazamiento constante. El método construct_problem() construye un problema de optimización QUBO como una instancia de QuadraticProgram, que se utiliza para definir el problema QP utilizando variables binarias. El método solve_problem() resuelve el problema QP construido en el paso anterior a través de la clase MinimumEigenOptimizer utilizando SamplingVQE con parámetros predeterminados. El resultado de la optimización se devuelve, que es la solución óptima al problema del TSP. 

Saludos 


### Autora  👩‍🎓 👩‍💻
  Yudy Camila Fuentes Pardo
