# Explicación del código detallada:
## Flujo principal del código:
### Bloque principal:
![imagen](https://github.com/user-attachments/assets/6aace5a0-045b-46fb-901e-76773eeeb830)
Permite al jugador iniciar una nueva partida, cargar una partida guardada o salir del juego. El flujo general del juego está basado en un menú de opciones que se repite hasta que el jugador decide salir. A continuación, se detalla el funcionamiento de cada parte del código:
- Inicialización y Pantalla de Inicio:
  - Se inicializa la variable seguir en True, que controlará el bucle principal del juego.
  - Se llama a la función dibujoInicio() para mostrar una pantalla de inicio del juego.
- Bucle Principal del Juego:
  - El bucle while seguir: continuará ejecutándose mientras seguir sea True.
  - Dentro de este bucle, se muestra un menú con las opciones disponibles y se guarda la opción seleccionada en la variable op.
- Opción 1: Crear un Nuevo Personaje
  - Si el jugador elige la opción "1", se llama a la función crearPersonaje() para generar un nuevo personaje.
  - El personaje creado se asocia con un "ideal" (por ejemplo, un ideal como "pirata" o "marine") a través de la función ideales().
  - Se muestran detalles iniciales sobre el personaje, como su nombre, raza y lugar de nacimiento.
  - También se describe la infancia del personaje mediante la función infancia() y se menciona que el personaje inicia su aventura al cumplir la mayoría de edad.
- Opción 2: Cargar una Partida Guardada
  - Si el jugador elige la opción "2", se cargan las partidas guardadas a través de la función cargarPartidas().
  - Se muestra una lista de partidas guardadas y se permite al jugador elegir una partida con la función elegirPartida().
  - Si no se encuentra una partida guardada (es decir, si no se selecciona una válida), se crea una partida vacía.
  - Si la partida se carga correctamente, se asigna el personaje y los arcos de la historia guardados.
- Opción 3: Salir del Juego
  - Si el jugador elige la opción "3", la variable seguir se cambia a False, lo que termina el bucle principal y finaliza el juego.
  - Se muestra un mensaje de despedida utilizando la función mensajeSalida().
- Bucle del Juego:
  - Si el jugador ha creado un personaje o ha cargado una partida guardada, se llama a la función bucleJuego() para iniciar el ciclo de juego, donde el jugador puede interactuar con el mundo del juego y tomar decisiones que afecten su aventura.
- Validación de Opciones:
  -  Si el jugador selecciona una opción no válida, se muestra un mensaje de error indicando que la opción no es válida.
### Función dibujoInicio():
![imagen](https://github.com/user-attachments/assets/ae6a9618-3616-42a6-875c-3792f858a9ef)
Tiene como objetivo imprimir un diseño en ASCII (arte visual realizado únicamente con caracteres) en la consola cuando se inicia el juego. Este diseño funciona como una especie de bienvenida visual para el jugador, proporcionando una introducción gráfica antes de que el juego comience.\
El diseño en ASCII es una serie de caracteres organizados que, en su conjunto, forman una imagen o patrón visual. En este caso, el diseño incluye símbolos como cuadros (⬜⬛), colores representados mediante bloques de color (🟨, 🟥), y texto con palabras o símbolos decorativos. El propósito de esta función es dar un toque estético y atractivo al inicio del juego, mejorando la experiencia del usuario.\
Funcionamiento:
- Al ejecutar la función, se muestra una serie de líneas que forman una imagen.
- La imagen utiliza caracteres especiales de Unicode, como los cuadros blancos y negros (⬜⬛) y los bloques de colores (🟨, 🟥`), creando un patrón visual llamativo. Además, el diseño incluye texto en ASCII que puede mostrar el nombre del juego, el logotipo, o algún mensaje de bienvenida.
  
La función no recibe parámetros y simplemente realiza la impresión del diseño cuando es llamada. Es una forma sencilla de personalizar la pantalla de inicio de un juego o programa, haciéndolo más interactivo y visualmente interesante.
### Función mensajeSalida():
![imagen](https://github.com/user-attachments/assets/d6581981-b0af-4043-b4f3-23d62d58f1ce)
Imprime un mensaje de despedida en formato ASCII cuando el juego termina.
### Función elegirOpcion():
![imagen](https://github.com/user-attachments/assets/40276009-a694-4210-99bd-e8fcaf6d85de)
Se encarga de mostrar un diseño visual en ASCII en la consola y luego solicitar al jugador que ingrese una opción a través del teclado. Este diseño proporciona una introducción gráfica para hacer la experiencia más atractiva y dar un toque interactivo al momento en que el jugador debe tomar una decisión dentro del juego.\
Funcionamiento:
- Mostrar diseño ASCII: La función comienza mostrando una serie de textos en formato ASCII que presentan un diseño decorativo utilizando caracteres especiales. Estos diseños están divididos en tres bloques diferentes, los cuales sirven para captar la atención del jugador antes de que realice una acción.
- Solicitar una opción: Tras la presentación del diseño, la función solicita al jugador que ingrese una opción usando input(). Esto le permite al jugador seleccionar una opción entre varias posibles (como iniciar un nuevo juego, cargar una partida guardada, o salir).
- Retorno de la opción: Finalmente, la función captura la opción ingresada por el jugador y la retorna para ser utilizada en otras partes del programa, como el control del flujo del juego, dependiendo de la decisión tomada por el jugador.
### Función bucleJuego():
![imagen](https://github.com/user-attachments/assets/a9f0a589-7233-4a06-844d-2b7178c641d7)
- Entrada:
  - Ninguna
- Flujo de la ejecución del juego:
  - Muestra el arte del personaje usando el diccionario de este.
  - El jugador debe interactuar con el menú y tomar decisiones que afectan el progreso del personaje.
  - Condiciones iniciales: Si la edad del personaje supera su esperanza de vida, el juego termina automáticamente.
  - Menú de decisiones: Dependiendo de la opción seleccionada (1, 2, 3, 4, 5):
      1. Opción 1: Inicia la aventura. Si el personaje tiene un arco, se llevan a cabo diferentes eventos de la historia (combates, frutas, jefes, etc.).
      2. Opción 2: Entrenamiento, donde el personaje aumenta estadísticas (si es posible).
      3. Opción 3: El personaje decide retirarse.
      4. Opción 4 o 5: Guardar la partida y finalizar el juego.
- Eventos y subflujos:
  - Aventura:
      - Si el personaje enfrenta un enemigo, puede ganar o perder, con cambios en las estadísticas.
      - Puede encontrar frutas que debe consumir o descartar.
      - Si encuentra un jefe, el resultado del combate afecta al progreso de la historia.
      - Si el arco está completo o es "victoria", el personaje recibe un final dependiendo de su ideal.
  - Entrenamiento:
  - Si las estadísticas del personaje no superan un límite determinado, puede entrenar, lo que aumenta sus estadísticas y su edad.
- Salida:
    - Si el jugador opta por retirarse o terminar la aventura (tras un combate o un final específico), el juego termina.
    - El estado del personaje se guarda si se selecciona una opción para guardar la partida (opciones 4 y 5).
### Función muerteVejez():
![imagen](https://github.com/user-attachments/assets/34acbed3-6c2e-4912-a66f-abb2063eba96)
Simula el final de la vida de un personaje debido a la vejez. El mensaje mostrado depende del nivel de fama del personaje al momento de su muerte. Según la fama del personaje, el mensaje varía para reflejar su impacto en la historia o la falta del mismo.
- Flujo:
  - Si el nivel de fama del personaje es menor o igual a 2, se indica que el personaje vivió algunas aventuras, pero sin un gran impacto en el mundo.
  - Si la fama está entre 3 y 5, el personaje es reconocido como una leyenda vaga en los mares, pero no deja una huella profunda en la historia.
  - Si la fama se encuentra entre 6 y 8, se menciona que el personaje será recordado como un bravo guerrero del mar, aunque no alcanzó el estatus de leyenda.
  - Si la fama es mayor a 8, el personaje es considerado una leyenda, cuyo único enemigo fue el tiempo.
### Función menuJuego():
![imagen](https://github.com/user-attachments/assets/ff1752d4-022f-4bb0-8205-b688ed2d94c9)
Presenta un menú interactivo para que el jugador elija una acción dentro del juego. Muestra una serie de opciones disponibles y luego captura la entrada del usuario para determinar qué acción se debe tomar.
- Flujo:
  - Se imprime un menú con las siguientes opciones:
    1. 1 Seguir los ideales del personaje y lanzarse a la aventura.
    2. 2 Entrenar para mejorar las estadísticas del personaje.
    3. 3 Retirarse del juego.
    4. 4 Guardar el progreso de la partida.
    5. 5 Salir del juego y guardar la partida.
- La función solicita al usuario que elija una opción a través de un input y retorna la opción seleccionada para su posterior procesamiento en otras partes del código.
### Función modificarProbabilidades(isla):
![imagen](https://github.com/user-attachments/assets/178f9db5-bfa2-410d-b2df-717bd6ab5732)
La función modificar_probabilidades(isla) ajusta las probabilidades relacionadas con los arcos de historia del juego según la isla de nacimiento del personaje. Si el personaje nace en una isla principal de un arco, las probabilidades de que ese arco se active aumentan.
- Flujo:
  - La función recibe como parámetro el nombre de la isla donde el personaje ha nacido.
  - Recorre todos los arcos disponibles en la lista arcos.
  - Si el nombre de la isla coincide con el nombre de la isla principal de un arco (arco[0]), se incrementa la probabilidad de que ese arco ocurra, aumentando el valor almacenado en arco[2] (probabilidad asociada al arco).
### Función selectorDeArco():
![imagen](https://github.com/user-attachments/assets/bf628aa7-11f0-49ce-bd3e-e6fd303e9b40)
Selecciona un arco de historia para el personaje basado en las probabilidades asociadas a cada arco. Si no hay arcos disponibles, devuelve el valor "victoria".
- Flujo:
  - Verificación de disponibilidad de arcos: Primero, verifica si la lista arcos contiene elementos. Si no hay arcos disponibles, la función retorna "victoria".
  - Creación de lista de pesos: Si hay arcos disponibles, crea una lista pesos donde cada valor corresponde a la probabilidad asociada a cada arco. Esta probabilidad se encuentra en el tercer valor de cada sublista dentro de arcos (arco[2]).
  - Selección ponderada: Utiliza la función random.choices() para elegir un arco de manera ponderada, considerando las probabilidades definidas en pesos. La función selecciona un arco basado en la probabilidad asignada a cada uno, favoreciendo aquellos con mayor peso.
  - Retorno del arco seleccionado: Finalmente, la función retorna el arco elegido.


## Funciones necesarias para crear al personaje:
### Función crearPersonaje():
![imagen](https://github.com/user-attachments/assets/b1e3531c-1428-4996-a2b8-aca9b0eaee94)
Se encarga de generar un personaje completo para un juego de rol, con las siguientes características:
1. Nombre del Personaje: Al ejecutar el programa, se te pedirá que ingreses el nombre de tu personaje. Este será el nombre con el que lo identificarás durante el juego.
2. Selección Aleatoria de Raza: El personaje será asignado aleatoriamente a una raza de entre varias opciones. Cada raza tiene una probabilidad distinta de ser elegida para darle un toque único a cada partida.
3. Generación de Atributos:\
Los atributos del personaje (como salud, ataque, defensa, etc.) se generan aleatoriamente dentro de un rango específico, pero también dependen de la raza seleccionada.
4. Arte ASCII: Dependiendo de la raza asignada, el personaje recibe un arte ASCII representativo que visualiza su raza de forma gráfica. Este arte puede ser mostrado en el juego, creando una experiencia visual más inmersiva.
5. Zona de Nacimiento Aleatoria: Además de la raza y los atributos, el personaje recibirá una zona de nacimiento aleatoria que determinará su "origen". Este detalle se incluye como parte del mundo del juego.
### Función islaNacimiento():
![imagen](https://github.com/user-attachments/assets/2e1debbb-1855-4117-bfb8-585c2c3b76b1)
Dependiendo de la zona (East Blue, West Blue, North Blue, South Blue, Grand Line o Red Line), el personaje recibe bonificaciones o penalizaciones en sus atributos: salud (HP), defensa (DEF), ataque (ATQ) y velocidad (VEL).\
Zonas y Efectos:
| **Zona**        | **Efecto en HP** | **Efecto en DEF** | **Efecto en ATQ** | **Efecto en VEL** |
|-----------------|------------------|-------------------|-------------------|-------------------|
| **East Blue**   | +5%              | N/A               | N/A               | N/A               |
| **West Blue**   | N/A              | +5%               | N/A               | N/A               |
| **North Blue**  | N/A              | N/A               | +5%               | N/A               |
| **South Blue**  | N/A              | N/A               | N/A               | +5%               |
| **Grand Line**  | -5%              | +5%               | +5%               | +5%               |
| **Red Line**    | N/A              | +10%              | N/A               | -5%               |

Cada zona tiene probabilidades diferentes de ser seleccionada, y dentro de estas una isla es elegida aleatoriamente como la de nacimiento del personaje.
### Función ideales():
![imagen](https://github.com/user-attachments/assets/25a1e650-6c8d-4bdb-8f55-9ba597cb2a89)
asigna un "ideal" (como pirata, bandido, revolucionario, etc.) al personaje según su lugar de nacimiento. Los valores posibles varían dependiendo de la isla de origen, y algunos lugares de nacimiento tienen un sistema de probabilidades ajustado para generar un resultado más específico.\
Zonas y Resultados:
- Isla de la Armada Revolucionaria: El ideal será aleatoriamente pirata, bandido o revolucionario.
- Mary Geoise: El personaje puede ser tenryubito, esclavo o sirviente. Si es tenryubito, puede tener eventos aleatorios (traición, caballero sagrado o noble), lo que afectará su ideal:
  - Traición: Puede ser pirata o revolucionario.
  - Caballero sagrado: Se convierte en caballero sagrado.
  - Noble: El personaje sigue siendo noble.
- Otros lugares de nacimiento: El ideal será aleatorio entre pirata, marine, bandido o revolucionario.
### Función infancia()
![imagen](https://github.com/user-attachments/assets/17f04515-12b3-431f-a756-adba8ba2dc44)
Dependiendo del "ideal" del personaje, sus atributos (ataque, defensa, velocidad y salud) se verán afectados de la siguiente manera:
| **Ideal**            | **Ataque (atq)** | **Defensa (def)** | **Velocidad (vel)** | **Salud (hp)**   |
|----------------------|------------------|-------------------|---------------------|------------------|
| **Pirata/Marine**     | +5%              | +5%               | +5%                 | +5%              |
| **Revolucionario**    | +5%              | +0.5%             | +0.5%               | -15%             |
| **Bandido**           | No cambia         | No cambia          | +25%                | -15%             |
| **Caballero Sagrado** | +15%             | +15%              | +15%                | +15%             |
| **Noble**             | -50%             | -50%              | -50%                | N/A       |

Descripción de los Efectos
1. **Pirata o Marine**: El personaje, inspirado por su ídolo, recibe un aumento del 5% en todos sus atributos.
2. **Revolucionario**: La vida llena de adversidades fortalece su ataque, pero reduce su salud en un 15%.
3. **Bandido**: El personaje, forjado en la miseria, tiene un aumento significativo en su velocidad, pero una penalización en salud.
4. **Caballero Sagrado**: Criado en la nobleza y entrenado desde joven, el personaje recibe una mejora del 15% en todos sus atributos.
5. **Noble**: Nacido en un entorno privilegiado, el personaje sufre una gran penalización en todos sus atributos, excepto en salud.
## Funciones necesarias para cargar y guardar paridas:
### Función guardarPartida:
![imagen](https://github.com/user-attachments/assets/d374dc7b-3e79-4eaf-9da4-4e380c2b78ea)
Esta función carga las partidas guardadas desde un archivo JSON. Si el archivo no existe o está corrupto, devuelve una lista vacía.
- Entrada:
  - No tiene parámetros de entrada.
- Salida:
  - Retorna una lista con los datos de las partidas guardadas si el archivo es válido. Si el archivo no existe o está corrupto, retorna una lista vacía [].
- Manejo de errores:
  - Si el archivo no se encuentra (FileNotFoundError) o no se puede leer correctamente (json.JSONDecodeError), la función maneja el error y devuelve una lista vacía.
### Función elegirPartida():
![imagen](https://github.com/user-attachments/assets/1c8fae27-e1cb-4731-aa98-dfad64b74a7c)
Permite al jugador seleccionar una partida guardada. Si no hay partidas disponibles, muestra un error y retorna "null". Si la selección es inválida, solicita al jugador que intente nuevamente.
- Entrada:
  - Ninguna.
- Salida:
  - Retorna la partida seleccionada o "null" si no hay partidas guardadas.
- Flujo:
  1. Carga las partidas guardadas con cargarPartidas().
  2. Si hay partidas, muestra una lista y pide al jugador seleccionar una.
  3. Valida la selección y retorna la partida seleccionada o pide un nuevo intento si es inválida.
### Función guardarPartida():
![imagen](https://github.com/user-attachments/assets/9887b802-3ecb-4140-85aa-2a4fa612d829)
Guarda o actualiza la partida actual en un archivo JSON. Si no se proporciona un ID, crea una nueva partida con un ID único. Si se proporciona un ID, actualiza la partida correspondiente.
- Entrada:
  - id (opcional): El ID de la partida a actualizar. Si es None, se crea una nueva partida.
- Salida:
  - No retorna ningún valor, pero imprime mensajes de éxito o error.
- Flujo:
  1. Carga las partidas guardadas con cargarPartidas().
  2. Si no se proporciona un id, se crea una nueva partida con un ID único.
  3. Si se proporciona un id, se actualiza la partida correspondiente con los datos del personaje y los arcos.
  4. Guarda las partidas actualizadas en el archivo OnePieceGame.json.
  5. Si ocurre un error durante el proceso, imprime un mensaje de error.
