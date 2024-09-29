# ReboundProyecto_1
Código de Rebound para el proyecto 1 de investigación de Medio Circunestelar y Sistemas Planetarios, escrito en Google Colab:

Utilizamos Rebound con unidades de km, yr, kg para distancia, tiempo y masa respectivamente puesto ya que las masas y distancias del sistema no son comparables a masas solares y UA respectivamente, se hace este cambio para trabajar con números más sencillos. 

El código consta de 7 simulaciones, y todas comparten el mismo "setup":

Introducimos como masa central del sistema a la Tierra, luego colocamos la Luna con masa, distancia y ángulo definidos, para luego agregar una partícula sin masa en un ángulo de ±π/3 (según el punto de Lagrange que se esté analizando en esa simulación) con respecto al ángulo de la Luna. Luego, la velocidad de rotación de la Luna se calcula a partir de la aceleración que genera la fuerza gravitatoria entre ella y la Tierra, y a la velocidad de la partícula se le debe aplicar una rotación de coordenadas como consecuencia de que su velocidad se define respecto a la de la Luna.

Analizando las simulaciones por separado:

Primera simulación:
Estudiamos la estabilidad de una partícula ubicada en L4, siendo la primera instancia donde utilizamos Rebound de forma totalmente autónoma, por lo que fuimos variando parámetros y haciendo un gráfico final sin animación, todo con fines de acostumbrarnos al software.

Segunda simulación:
Ahora queremos animar el movimiento de las partículas de la primera simulación, por lo que incluimos las librerías "FuncAnimation" de "matplotlib.animation" que contiene la función animación, y la librería "HTML" de "IPython.display", esto para que la animación se ejecute correctamente en el entorno de Google Colab, y creamos entonces la animación para el mismo sistema anterior, lo que ilustra mejor la estabilidad de la partícula en el punto L4. Luego, en la sección de velocidades iniciales, incrementamos en 0,001 la velocidad inicial de la partícula para observar si esta se mantiene en órbita estable. Aquí, tanteamos valores de proporción para la velocidad de la partícula, y encontramos que si vx_part4, vy_part4 < 0,001 la partícula vuelve a estar en la misma órbita, pero si es mayor, esta se sale de la órbita; notar que al ser una proporción, a mayor valor de velocidad más rápido es su desórbita (pruebe, por ejemplo, con el doble de la velocidad en x e y).  

Tercera simulación:
Se colocan partículas sin masa tanto en L4 como en L5, y ahora se agregó una partícula sin masa en un ángulo arbitrario π/6 para ver cómo este evoluciona comparado a las partículas estables, donde efectivamente vemos que coincide con que las partículas estables se mantienen en su órbita mientras la partícula arbitraria tiende a una órbita inestable.

Cuarta simulación:
Se sigue el sistema de la segunda simulación, pero se cambió la particula a L5 y se le dió una masa de 5e23 kg para hacer notar que el sistema cambia cuando se introduce una masa de magnitud considerable, transformándose en un problema de tres cuerpos y donde ya no se sostienen los puntos Lagrangianos.

Quinta simulación:
Ahora queremos analizar una distribución de partículas ubicadas aleatoriamente en la órbita Lunar. A partir de este planteamiento, se observará que partículas al azar fueron colocadas en los puntos Lagrangianos L4 y L5, por ende estas logran mantener una trayectoria estable y durante el intervalo de tiempo se hace notar una mayor densidad de partículas en ese tramo. Para las partículas que fueron ubicadas de [0,2π]-{-π/3,π/3}, se logra apreciar en el gráfico de distribución como sus trayectorias difieren del trazo orbital.

Sexta simulación:
Esta simulación es muy similar a la primera, pero aquí nos interesa observar si existe una configuración triangular estable para una relación de masas tan baja como el sistema Plutón-Caronte. Para ello, creamos un sistema con las masas de Plutón y Caronte y colocamos una partícula sin masa en el supuesto punto de Lagrange L4 que debería crearse, pero vemos que efectivamente no se mantiene ahí pues el sistema no cumple con los requisitos de proporción de masas entre los cuerpos principales. Asumimos que para L5 ocurrirá lo mismo dada la alta simetría de estos dos puntos Lagrangianos. 

Séptima simulación:
Se plantea el sistema binario de Sirio A, Sirio B y una partícula sin masa ubicada en un supuesto L4, nuevamente como la diferencia de masas es mínima (la masa de Sirio A es casi 2 veces la de Sirio B), este sistema no puede admitir puntos de Lagrange, lo que se ve reflejado en el comportamiento del sistema entero.
