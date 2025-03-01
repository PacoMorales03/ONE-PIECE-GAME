> [!NOTE]
> Los dibujos ascii están generados a partir de imágenes usando la página [https://emojicombos.com], esta página también cuenta con diseños ya hechos que he usado
# Explicación del código detallada:
En este apartado voy a realizar una explicación más detallada de este proyecto, más allá de los comentarios ya realizados en el código.\
He dividido el código en 3 secciones distintas:
- Flujo principal
- Funciones necesarias para cargar y guardar partida
- Finales
## Flujo principal del código:
Aquí se encuentran tanto el bloque principal como las funciones utilizadas para el funcionamiento general de el código. 
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
      1. Opción 1: Inicia la aventura. Si el personaje tiene un arco, se llevan a cabo diferentes eventos de la historia.
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
### Función SelectorDeEvento():
![imagen](https://github.com/user-attachments/assets/77599d49-0b87-4479-b890-e528964b2bdf)
Selecciona aleatoriamente un evento que el personaje debe enfrentar, con una distribución de probabilidades. Si el personaje tiene una fruta, los posibles eventos se limitan a ciertos tipos, mientras que si no tiene una fruta, los eventos disponibles incluyen otros tipos con probabilidades ajustadas.
- Flujo:
  - Verificación de fruta asignada: La función verifica si el personaje tiene una fruta asignada (personaje["fruta"]). Si el personaje no tiene una fruta asignada (es decir, None), se procede a la primera lógica de selección de eventos.
    - Si no tiene fruta:
      - Se definen tres posibles eventos: "enemigo", "fruta", y "boss".
      - La selección de estos eventos se hace de manera ponderada, con probabilidades asignadas de 40% para "enemigo", 20% para "fruta", y 40% para "boss". Estas probabilidades definen cómo se distribuyen los eventos durante el juego.
      - Si tiene una fruta:
          - Los eventos posibles se limitan a "enemigo" y "boss" (ya que no puede obtener otra fruta).
          - La selección de eventos se hace aleatoriamente entre estos dos, sin ponderación.
  - Selección de evento: Dependiendo de la situación, el evento se elige utilizando random.choices() para ponderar las probabilidades (cuando no tiene fruta) o random.choice() cuando la selección es aleatoria entre "enemigo" y "boss" (si tiene una fruta).
  - Retorno del evento seleccionado: Finalmente, la función retorna el evento elegido, que puede ser "enemigo", "fruta" o "boss".
### Función combate(name,es_boss):
![imagen](https://github.com/user-attachments/assets/678bda02-7641-45b1-96c1-f143cb975850)
Maneja un enfrentamiento entre el personaje y un enemigo o jefe. Dependiendo de si el combate es contra un jefe o un enemigo común, las estadísticas y el flujo del combate cambian. El jugador tiene la opción de pelear o huir, y el combate se resuelve por turnos en función de las estadísticas de ambos personajes.
- Parámetros:
  - name (str): El nombre del enemigo o jefe contra el cual se combate.
  - es_boss (bool): Un valor booleano que indica si el combate es contra un jefe (True) o contra un enemigo común (False).
- Flujo:
  1. Selección de enemigo:
      - Si el combate es contra un jefe, las estadísticas se toman de un diccionario predefinido de jefes (bosses), que contiene valores como hp, atq, def, y vel.
      - Si el combate es contra un enemigo común, las estadísticas del enemigo se generan aleatoriamente en función de las estadísticas del personaje.
  2. Inicio del combate:
      - Se guarda la vida original del personaje antes de iniciar el combate, para que, en caso de huir, se pueda restaurar.
      - Se muestran las estadísticas del personaje y del enemigo, incluyendo la vida, ataque, defensa, y velocidad.
  3. Opciones de acción:
     - El jugador tiene dos opciones:
         - Pelear: Si el jugador elige pelear, se resuelven los turnos de combate.
         - Huir: El jugador puede intentar huir, con una probabilidad determinada por la velocidad del jugador y el enemigo. Si tiene éxito, el combate termina y el jugador "escapa".
      - Si la opción elegida no es válida, el sistema sigue pidiendo al jugador que ingrese una opción válida.
  4. Resolución del combate:
     - Turnos de combate:
         - Si el personaje tiene mayor velocidad que el enemigo, el jugador ataca primero.
         - Si el enemigo tiene mayor velocidad, el enemigo ataca primero.
      - En cada turno:
        - El jugador inflige daño al enemigo según su ataque y la defensa del enemigo.
        - El enemigo inflige daño al jugador según su ataque y la defensa del jugador.
      - Se repiten los turnos hasta que uno de los dos personajes pierda toda su vida (hp).
  5. Resultado:
     - Si el enemigo pierde todo su hp: El jugador gana el combate, sus estadísticas (vida, ataque, defensa, velocidad) aumentan en función de las estadísticas del enemigo derrotado, y el combate termina con una victoria.
     - Si el jugador pierde todo su hp: El jugador pierde el combate y el juego devuelve el resultado como "derrota".
  6. Retorno:
     - "victoria": Si el jugador gana el combate.
     - "derrota": Si el jugador pierde el combate.
     - "escapas": Si el jugador huye con éxito del combate.
### Función mostrarEstadisticas():
![imagen](https://github.com/user-attachments/assets/f3a25812-d0f6-49a3-93f6-e37078fc8a19)
Se encarga de mostrar de manera visual y representativa las estadísticas del personaje, usando iconos para cada atributo. Las estadísticas mostradas incluyen la vida (hp), el ataque (atq), la defensa (def), y la velocidad (vel). La cantidad de iconos por atributo es proporcional al valor de cada estadística, proporcionando una representación fácil de interpretar.
- Flujo:
  1. Generación de iconos:
     - Para cada atributo del personaje (hp, atq, def, vel), se genera una cadena de texto compuesta por iconos repetidos:
       - ❤️ para la vida (hp), con una frecuencia proporcional a la vida dividida por 10.
       - ⚔️ para el ataque (atq), con una frecuencia proporcional al ataque dividido por 5.
       - 🛡️ para la defensa (def), con una frecuencia proporcional a la defensa dividida por 5.
       - 👢 para la velocidad (vel), con una frecuencia proporcional a la velocidad dividida por 5.
  2. Impresión de las estadísticas:
     - Se imprime el nombre del personaje seguido de sus estadísticas representadas visualmente con los iconos generados.
  3. Formato:
     - La salida sigue un formato claro y estructurado, con etiquetas para cada estadística (Vida, Ataque, Defensa, Velocidad) y los iconos correspondientes.
 ### Función selectorFruta():
![imagen](https://github.com/user-attachments/assets/4da5477a-b22a-4f81-b19a-a26372fb6eb3)
Simula la selección aleatoria de una fruta de la lista frutas. Dependiendo de la fruta seleccionada, el personaje tiene sus atributos modificados, como hp, def, atq, y vel.\
- Uso de random.choice(frutas):
  - Esto selecciona aleatoriamente una fruta de la lista frutas.
- Modificación de los atributos:
  - Cada fruta tiene un efecto específico sobre el personaje:
    
| Fruta del Diablo     | Aumento de Stats                              | Disminución de Stats   |
|----------------------|-----------------------------------------------|------------------------|
| Gomu Gomu no Mi      | HP +10%, DEF +10%                             | Vel -10%               |
| Mera Mera no Mi      | ATQ +20%, Vel +10%                            | DEF -10%               |
| Hie Hie no Mi        | DEF +20%, ATQ +10%                            | Vel -10%               |
| Pika Pika no Mi      | Vel +30%, ATQ +15%                            | DEF -10%               |
  - Impresión de efectos visuales:\
    Para cada fruta, el código imprime una representación artística (en forma de texto) y una breve descripción de los poderes que otorga la fruta.
### Función consumirFruta(fruta):
![imagen](https://github.com/user-attachments/assets/5c360db7-0469-41f1-9303-94f9d19d6668)
Permite que un personaje consuma una fruta del diablo, asignándosela a su inventario y eliminándola de la lista de frutas disponibles para otros personajes.
- Parámetros:
  - fruta (str): El nombre de la fruta del diablo que el personaje va a consumir.
- Efectos:
  - Asigna la fruta seleccionada al personaje, almacenando su nombre en el diccionario personaje["fruta"].
  - Elimina la fruta de la lista frutas, de manera que ya no pueda ser consumida por otros personajes.
### Función descartarFruta():
![imagen](https://github.com/user-attachments/assets/5dd2770a-95ba-4a1c-bbb6-fa91b824963e)
Permite descartar una fruta del diablo de la lista de frutas disponibles. Elimina la fruta especificada de la lista, lo que significa que ya no estará disponible para ser consumida por ningún personaje.
- Parámetros:
  - fruta (str): El nombre de la fruta del diablo que se va a descartar.
- Efectos:
  - Elimina la fruta especificada de la lista frutas, asegurando que ya no pueda ser utilizada ni consumida.



## Funciones necesarias para crear al personaje:
Aquí están las funciones encargadas de inicializar el personaje y necesarias para el juego 
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

## Finales
Aquí se encuentran los distintos finales psoibles del juego
### Función muerteVejez():
![imagen](https://github.com/user-attachments/assets/34acbed3-6c2e-4912-a66f-abb2063eba96)
Simula el final de la vida de un personaje debido a la vejez. El mensaje mostrado depende del nivel de fama del personaje al momento de su muerte. Según la fama del personaje, el mensaje varía para reflejar su impacto en la historia o la falta del mismo.
- Flujo:
  - Si el nivel de fama del personaje es menor o igual a 2, se indica que el personaje vivió algunas aventuras, pero sin un gran impacto en el mundo.
  - Si la fama está entre 3 y 5, el personaje es reconocido como una leyenda vaga en los mares, pero no deja una huella profunda en la historia.
  - Si la fama se encuentra entre 6 y 8, se menciona que el personaje será recordado como un bravo guerrero del mar, aunque no alcanzó el estatus de leyenda.
  - Si la fama es mayor a 8, el personaje es considerado una leyenda, cuyo único enemigo fue el tiempo.
### Función mensajeDerrota():
![imagen](https://github.com/user-attachments/assets/e63f4e44-4781-4c6b-ba6e-6b18826a7460)
Simula el final de la vida de un personaje debido a la muerte en combate. El mensaje mostrado depende del nivel de fama del personaje al momento de su muerte. Según su fama, el mensaje varía para reflejar su impacto en la historia o la falta del mismo.
- Flujo:
  - Si el nivel de fama del personaje es menor o igual a 2, se indica que su muerte no deja huella en la historia, siendo olvidado rápidamente.
  - Si la fama está entre 3 y 5, se menciona que el personaje comenzaba a ser reconocido, pero su muerte llega antes de consolidar su legado.
  - Si la fama se encuentra entre 6 y 8, se destaca que el personaje era un guerrero en ascenso, pero su caída impide que alcance la categoría de leyenda.
  - Si la fama es mayor a 8, se reconoce que incluso las leyendas pueden caer, pero su legado será recordado por generaciones.
### Función retirarse():
![imagen](https://github.com/user-attachments/assets/3180278d-c3ec-4d1d-b99b-1da3dfc72ced)
Simula el retiro de un personaje antes de morir. El mensaje mostrado varía dependiendo de su nivel de fama al momento de retirarse, reflejando el impacto que tuvo en la historia.
- Flujo:
  - Se genera un número aleatorio de hijos entre 0 y 5.
  - Se menciona la edad en la que el personaje fallece tras su retiro.
  - Si la fama es menor o igual a 2, su nombre será olvidado con el tiempo.
  - Si la fama está entre 3 y 5, su historia será recordada vagamente en los mares.
  - Si la fama está entre 6 y 8, será recordado como un bravo guerrero, pero sin alcanzar la inmortalidad de una leyenda.
  - Si la fama es mayor a 8, se le considerará una leyenda cuyo único enemigo fue el paso del tiempo.
### Función finalNoble():
![imagen](https://github.com/user-attachments/assets/82d9edd9-f677-4573-99d8-cda83e180cfb)
Describe el final de un personaje noble, en un contexto donde se refleja su vida sin escrúpulos ni piedad, observando guerras y batallas sin afectarse. La muerte del personaje se describe de manera sombría, destacando su vida llena de poder y su muerte sin grandes logros ni sufrimiento.
### Función victoriaPirata()
![imagen](https://github.com/user-attachments/assets/b1bc9554-7239-4f99-8ec5-8b5e1d7d9e43)
Muestra un mensaje de victoria si el personaje ha alcanzado su sueño como pirata, con su nombre siendo reconocido por los mares y su bandera ondeando alto.
### Función victoriaMarine():
![imagen](https://github.com/user-attachments/assets/388ceb15-cc6d-4508-8927-4f34c158fef9)
Muestra un mensaje de victoria si el personaje ha logrado su sueño como marine, convirtiéndose en un símbolo de justicia y orden en los mares.
### Función victoriaRevolucionario():
![imagen](https://github.com/user-attachments/assets/daa1081f-3e93-4d4e-8ba9-559a9c6f3f41)
Muestra un mensaje de victoria si el personaje sigue el ideal revolucionario, desafiando al Gobierno Mundial y liberando al pueblo.
### Función victoriaCaballeroSagrado():
![imagen](https://github.com/user-attachments/assets/d1bac9fb-4c22-4b2c-85d0-786f37234721)
Muestra un mensaje de victoria si el personaje sigue el ideal de caballero sagrado, siendo reconocido por los Dragones Celestiales y gobernando desde la élite del mundo.
### Función victoriaBandido():
![imagen](https://github.com/user-attachments/assets/1f79f363-a8eb-43dc-9acf-74e830d587a0)
Muestra un mensaje de victoria si el personaje sigue el ideal de bandido, imponiendo su propia ley y dominando mares y tierras sin rendir cuentas a nadie.

# Pruebas
En este apartado se adjuntarán distintas pruebas, tanto de caja blanca como de caja negra.
## Pruebas de caja blanca:
A lo largo del código he implementado distintas estructuras lógicas para el manejo de errores, entre ellas try-except
### Ejemplo 1:
![imagen](https://github.com/user-attachments/assets/551bdbc5-f6a0-403f-b695-2136072cf3c5)
En este caso el try-except se encarga de controlar que el dato introducido sea numérico y en caso de no serlo no termine el programa por un error
### Ejemplo 2:
![imagen](https://github.com/user-attachments/assets/1333d55a-31c7-4497-a6e8-c3675ceda511)
Aquí en caso de no poder abrir el archivo json con las partidas guardadas devolvería una lista vacía, esto se hace así para que posteriormente no genere un error al intentar seleccionar la partida.
A parte de la gestión de errores con los try-excepts he tratado de llevar una buena organización a la hora de manejar todas las opciones posibles cada vez que ha sido necesario, para esto he usado if,elif y else anidados.
### Ejemplo 3:
![imagen](https://github.com/user-attachments/assets/7c514779-507f-45b8-8f43-39ebab51ae97)
En este caso se cubren todas las opciones disponibles usando if-else. Esto hace que no de lugar a posibles errores en cuánto al funcionamiento al no haber opciones no evaluadas.
## Pruebas de caja negra:
### Menú principal
![imagen](https://github.com/user-attachments/assets/34dc458c-591c-4280-bbb3-35bc227be967)
### Crear partida:
![imagen](https://github.com/user-attachments/assets/b4ffb18e-a74f-4ef9-ac43-f62b93e2d9fc)
### Lanzarte a la aventura
![imagen](https://github.com/user-attachments/assets/0b2e2808-4428-4665-b099-2e1bcd6983d9)
### Pelear
![imagen](https://github.com/user-attachments/assets/427215ba-f509-4faa-b365-c3a31269055e)  
Durante esta prueba me he dado cuenta de que hay que reajustar el daño del combate para siempre hacer un mínimo de daño, por lo que he corregido eso:
![imagen](https://github.com/user-attachments/assets/48445970-d278-4d55-a3e1-8754d3f6a146)
Ahora si el resultado del ataque menos la defensa es menor a 10 se inflingirá siempre 10 de daño. 
### Huida
![imagen](https://github.com/user-attachments/assets/e0c182fa-91d9-465a-99a1-b57927609c72)
### Entrenar
![imagen](https://github.com/user-attachments/assets/6f02cfbf-c119-47a1-a5fe-6fd32bee37a5)
### Retirarte
![imagen](https://github.com/user-attachments/assets/565bf828-650a-4e3c-989b-ceb14a192aee)
### Cargar partida sin partidas guardadas
![imagen](https://github.com/user-attachments/assets/9c2fa45e-ca57-4ada-a9f5-f8a555b0a9e6)
### Guardar partida y guardar y salir
![imagen](https://github.com/user-attachments/assets/28097081-8a5d-4ddb-93ed-57b7b416f5d7)
### Cargar partida
![imagen](https://github.com/user-attachments/assets/58c6f0ac-5e60-4ff9-87fa-145801de58fb)
### Salir
![imagen](https://github.com/user-attachments/assets/192833c3-8c18-4b64-adf3-60995ea64ba7)
