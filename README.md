# Explicación del código detallada:
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
### Función elegirOpcion():
![imagen](https://github.com/user-attachments/assets/40276009-a694-4210-99bd-e8fcaf6d85de)
Se encarga de mostrar un diseño visual en ASCII en la consola y luego solicitar al jugador que ingrese una opción a través del teclado. Este diseño proporciona una introducción gráfica para hacer la experiencia más atractiva y dar un toque interactivo al momento en que el jugador debe tomar una decisión dentro del juego.\
Funcionamiento:
- Mostrar diseño ASCII: La función comienza mostrando una serie de textos en formato ASCII que presentan un diseño decorativo utilizando caracteres especiales. Estos diseños están divididos en tres bloques diferentes, los cuales sirven para captar la atención del jugador antes de que realice una acción.
- Solicitar una opción: Tras la presentación del diseño, la función solicita al jugador que ingrese una opción usando input(). Esto le permite al jugador seleccionar una opción entre varias posibles (como iniciar un nuevo juego, cargar una partida guardada, o salir).
- Retorno de la opción: Finalmente, la función captura la opción ingresada por el jugador y la retorna para ser utilizada en otras partes del programa, como el control del flujo del juego, dependiendo de la decisión tomada por el jugador.
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
- East Blue: +5% HP
- West Blue: +5% DEF
- North Blue: +5% ATQ
- South Blue: +5% VEL
- Grand Line: -5% HP, +5% DEF, ATQ y VEL
- Red Line: +10% DEF, -5% VEL

Cada zona tiene probabilidades diferentes de ser seleccionada, y una isla dentro de esa zona es elegida aleatoriamente.
