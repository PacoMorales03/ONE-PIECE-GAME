# Explicación del código detallada:

> [!NOTE]
> Bloque principal
### Bloque principal:
![imagen](https://github.com/user-attachments/assets/6aace5a0-045b-46fb-901e-76773eeeb830)
Permite al jugador iniciar una nueva partida, cargar una partida guardada o salir del juego. El flujo general del juego está basado en un menú de opciones que se repite hasta que el jugador decide salir. A continuación, se detalla el funcionamiento de cada parte del código:\
- Inicialización y Pantalla de Inicio:\
        Se inicializa la variable seguir en True, que controlará el bucle principal del juego.\
        Se llama a la función dibujoInicio() para mostrar una pantalla de inicio del juego.
- Bucle Principal del Juego:\
        El bucle while seguir: continuará ejecutándose mientras seguir sea True.\
        Dentro de este bucle, se muestra un menú con las opciones disponibles y se guarda la opción seleccionada en la variable op.
- Opción 1: Crear un Nuevo Personaje\
        Si el jugador elige la opción "1", se llama a la función crearPersonaje() para generar un nuevo personaje.\
        El personaje creado se asocia con un "ideal" (por ejemplo, un ideal como "pirata" o "marine") a través de la función ideales().\
        Se muestran detalles iniciales sobre el personaje, como su nombre, raza y lugar de nacimiento.\
        También se describe la infancia del personaje mediante la función infancia() y se menciona que el personaje inicia su aventura al cumplir la mayoría de edad.
- Opción 2: Cargar una Partida Guardada\
        Si el jugador elige la opción "2", se cargan las partidas guardadas a través de la función cargarPartidas().\
        Se muestra una lista de partidas guardadas y se permite al jugador elegir una partida con la función elegirPartida().\
        Si no se encuentra una partida guardada (es decir, si no se selecciona una válida), se crea una partida vacía.\
        Si la partida se carga correctamente, se asigna el personaje y los arcos de la historia guardados.
- Opción 3: Salir del Juego
        Si el jugador elige la opción "3", la variable seguir se cambia a False, lo que termina el bucle principal y finaliza el juego.\
        Se muestra un mensaje de despedida utilizando la función mensajeSalida().
- Bucle del Juego:\
        Si el jugador ha creado un personaje o ha cargado una partida guardada, se llama a la función bucleJuego() para iniciar el ciclo de juego, donde el jugador puede interactuar con el mundo del juego y tomar decisiones que afecten su aventura.
- Validación de Opciones:\
        Si el jugador selecciona una opción no válida, se muestra un mensaje de error indicando que la opción no es válida.
