# ReboundProyecto_1
Código de Rebound para el proyecto 1 de Medio Circunestelar, escrito en Google Colab:

Utiliza Rebound con unidades de km, yr, kg para distancia, tiempo y masa respectivamente puesto que como las masas y distancias del sistema no son comparables a masas solares y UA respectivamente, se hace este cambio para trabajar con números más sencillos. 

El codigo consta de 7 simulaciones, y todas comparten el mismo "setup":

Introducimos como masa central del sistema a la tierra, luego colocamos la luna con masa, a una distancia y ángulo definidos, para luego colocar una partícula sin masa en un ángulo de ±π/3 (según el punto de Lagrange que se esté analizando en esa simulación) con respecto al ángulo de la luna. Luego, la velocidad de rotación de la luna se calcula a partir de la aceleración que genera la fuerza gravitatoria entre ella y la tierra, y a la velocidad de la partícula se le debe aplicar una rotación coordenadas como consecuencia de que su velocidad se define respecto a la de la luna.

Analizando las simulaciones por separado,

Primera simulación:
Estudiamos la estabilidad de una partícula ubicada en L4, siendo la primera instancia donde utilizamos rebound de forma totalmente autónoma, por lo que fuimos probando parámetros y haciendo un gráfico final sin animación, todo con fines de acostumbrarnos al software.

Segunda simulación:
Ahora queremos animar el movimiento de las partículas de la primera simulación, por lo que incluimos las librerias "FuncAnimation" de "matplotlib.animation" que contiene la funcion animación, y la libreria "HTML" de "IPython.display", esto para que la animación se ejecute correctamente en el entorno de Google Colab, y creamos entonces la animación para el mismo sistema anterior, lo que ilustra mejor la estabilidad de la partícula en el punto L4.

Tercera simulación:
Se colocan partículas sin masa tanto en L4 como en L5, y ahora se agregó una partícula sin masa en un ángulo arbitrario π/6 para ver cómo este evoluciona comparado a las partículas estables, donde efectivamente vemos que coincide con que las partículas estables se mantienen en su órbita mientras la partícula arbitraria tiende a una órbita caótica.

Cuarta simulación:
Se sigue el sistema de la segunda simulación, pero se cambió la particula a L5 y se le dió una masa de 5e23 kg para hacer notar que el sistema cambia cuando se introduce una masa de magnitud considerable, transformandose en un problema de tres cuerpos y donde ya no se sostienen los puntos lagrangianos.

Quinta simulación:
Ahora queremos analizar una distribución de partículas colocadas aleatoriamente en la órbita Lunar. A partir de este planteamiento, se observará que partículas al azar fueron colocadas en los puntos Lagrangianos L4 y L5, por ende estas lograron mantener una trayectoria estable y durante el intervalo de tiempo se hace notar una mayor densidad de partículas en ese tramo. Para las partículas que fueron ubicadas de [0,2π]-{-π/3,π/3}, se logra apreciar en el gráfico de distribución como sus trayectorias difieren del trazo orbital.

Sexta simulación:
Creamos un sistema con las masas de Plutón y Caronte, y colocamos una partícula sin masa en el supuesto punto de lagrange L4 que debería crearse, pero vemos que efectivamente no se mantiene ahí pues el sistema no cumple con los requisitos de diferencias de masas entre los cuerpos principales.

Séptima simulación:
Se plantea el sistema binario de Sirio A y Sirio B y una partícula sin masa, nuevamente como la diferencia de masas es mínima (la masa de Sirio A es casi 2 veces la de Sirio B), este sistema no puede admitir puntos de lagrange.
