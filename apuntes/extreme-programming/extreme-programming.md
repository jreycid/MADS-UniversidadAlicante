# eXtreme Programming #

## Historia de XP ##

El origen de Extreme Programming (XP) se encuentra en la comunidad
Smalltalk, en particular en la colaboración entre Kent Beck y Ward
Cunningham a finales de los 80 en temas relacionados con el diseño y
programación orientada a objetos. Por ejemplo, en 1989, publicaron el
artículo [A laboratory for teaching object-oriented
thinking](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.129.4074)
en el que introducen las tarjetas CRC para definir las
responsabilidades de las clases en un diseño orientado a objetos.

En 1996 Kent Beck comenzó a trabajar en el Chrysler Comprehensive
Compensation System ([proyecto C3](https://www.martinfowler.com/bliki/C3.html), en el que conoció a
Ron Jeffries. Se trató de un proyecto de gestión Chrysler que se
hizo famoso no por terminarse con éxito (fue cancelado en 1999) sino
por considerarse el proyecto en el que nació XP.

El proyecto comenzó realmente en 1993, como un intento de reemplazar y
unificar numerosos sistemas de nóminas _legacy_ basados en
COBOL. Martin Fowler comenzó a participar en él como consultor en esta
época. En 1995 se tomó la decisión de reescribir todo el sistema en el
lenguaje de programación Smalltalk y Kent Beck tomó la dirección del
proyecto. Allí puso en acción todas las prácticas que después tomaron
el nombre de _Extreme Programming_ (aunque había utilizado enfoques
similares en proyectos previos). Beck contó también con la
colaboración de Ron Jeffries en el equipo. Ron fue también otro autor
del manifiesto ágil y de numerosas publicaciones relacionadas con XP y
metodologías ágiles.
  
El software se puso en producción en 1997, realizando la gestión de
nóminas de alrededor de diez mil personas. El proyecto continuó,
intentando cubrir al resto de empleados, pero terminó fracasando y se
detuvo el desarrollo en 1999 (volviéndose a poner en funcionamiento el
sistema _legacy_ en COBOL). Para esa fecha las prácticas XP ya se
habían popularizado y habían demostrado su éxito en otros proyectos (a
pesar de que, paradójicamente, su proyecto inicial terminara
fracasando).

En 1999 Kent Beck recopila todas sus ideas sobre XP en su primera
edición del "libro blanco" de Extreme Programming, en el que establece
el conjunto de valores, principios y prácticas iniciales de XP.

La metodología se vuelve muy popular a finales de los 90, siendo la
metodología ágil más popular al final de la década. De hecho, de las
17 personas que elaboran el manifiesto ágil en 2001, 6 provenían de la
filosofía de XP.

A mediados del 2000, en 2004, Kent Beck publica la segunda edición de
su libro. Esta nueva edición contenía una versión más estructurada y
madura de la metodología. En la primera edición se definían 12
prácticas principales que en la segunda se modifican y se convierten
en 13 (distintas de las anteriores) y se suman 11 prácticas
secundarias. Algunos autores hablan de XP1 y XP2.

Las fechas de publicación de estos dos libros (finales de 1990s y
principios de 2000s) fueron el punto álgido del interés y la adopción
de XP. A partir aquí la metodología pierde popularidad y en la última
década y media ha sido sustituida por Scrum, una metodología más
general (menos orientada a desarrollo de software) que tiene roles y
ceremonias más establecidos y fáciles de replicar.

Sin embargo, paradójicamente, el interés por las prácticas XP no ha
dejado de crecer. Prácticas como el test driven development (TDD), la
refactorización, la integración continua o el pair programming son
cada vez más populares, aunque las encontramos en el marco de otras
corrientes como el [software
craftmanship](https://en.wikipedia.org/wiki/Software_craftsmanship).

<img src="imagenes/state-of-agile-practicas-desarrollo.png" width="450px" align="right"/>

De hecho, en el último informe sobre adopción de metodologías ágiles
[14th Annual State of Agile
Report](https://stateofagile.com/#ufh-i-615706098-14th-annual-state-of-agile-report/7027494)
en la lista de prácticas más populares (imagen derecha) aparecen
bastantes promovidas por XP: 

- Continuous integration (55%), 
- Refactoring (43%)
- Continuous delivery (41%)
- Pair programming (31%)
- Test Driven Development (30%)
- Collective Code Ownership (29%)

<table markdown="1">
<tr><td>

<img src="imagenes/xp-books.png" width="250px" align="right"/>

**Dos ediciones con bastantes diferencias**

La primera y la segunda edición del libro de Kent Beck _Extreme
Programming Explained_ tienen cambios notables. La primera edición fue
escrita antes del manifiesto ágil y con la idea de ser un texto
fundacional. Las prácticas son más específicas y orientadas a la
programación.

La segunda edición se escribió 5 años después, en 2004, y en ella se
modifican algo las prácticas, incluyendo más elementos humanos y de
dinámica de equipo, y reduciendo algo las orientadas a la
programación. Quizás Beck intentaba competir con Scrum, que ya estaba
extendiéndose mucho más que XP.

Es un ejercicio interesante leer ambas versiones y reflexionar sobre
cómo la primera versión se convirtió en la segunda. Cómo se han
modificado algunos nombres de algunas prácticas, o se ha dividido en
dos lo que originalmente era una única práctica (o viceversa).

Ambas formulaciones son compatibles y, de hecho, es recomendable
verlas como complementarias. En la sesión vamos a utilizar
principalmente la segunda edición, aunque incorporando elementos de la
primera.

</td></tr></table>


## Introducción rápida a XP ##

XP es una metodología ágil orientada específicamente al desarrollo de
software, no ofrece demasiadas soluciones para otras áreas cómo
gestión del portfolio, operaciones, marketing o ventas.

Tiene una especificación más ligera que otras metodologías
como Scrum, en donde se definen un conjunto muy detallado de
artefactos, roles y ceremonias. En XP se intenta hacer sólo lo que es
necesario para crear valor para el cliente.

### Prácticas de XP ###

El elemento central de XP son sus prácticas. En los siguientes
párrafos resumimos cómo sería el trabajo de un equipo de desarrollo
usando estas prácticas.

- Un desarrollador trabajando con XP participará en un equipo que se
siente unido, que trabaja en un espacio común con paredes llenas de
esquemas, fichas, y elementos informativos y que desarrolla su faena a
pleno rendimiento, trabajando de forma sostenida y sin presión ni
agobios.

- El equipo diseña el software escribiendo en tarjetas (denominadas
_historias_) las nuevas funcionalidades a implementar usando un
lenguaje de negocio común. El equipo construye la aplicación usando un
enfoque iterativo y evolutivo, basado en un diseño incremental.

- Semanalmente los clientes definen las historias y se añaden a la
aplicación, definiendo primero los tests que deben cumplir y
trabajando en parejas para escribir el código que hace pasar esos
tests. Continuamente se compila la aplicación, se integra y se pasan
todos los tests, en un proceso que debería ser muy rápido (menos de 10
minutos). 

- Cada tres meses se reflexiona sobre la dirección global del proyecto,
estableciendo nuevas prioridades y analizando posibles mejoras en el
proceso. 


### Resultado de aplicar XP ###

Mediante el uso de XP podremos:

- Reducir el riesgo del proyecto.
- Mejorar la respuesta antes cambios en el negocio.
- Mejorar la productividad a lo largo de toda la vida del software.
- Hacer más divertido el trabajo del equipo construyendo el software.
- Adaptarnos mejor a requisitos vagamente formulados o que cambian en
  el tiempo.

XP es un intento de reconciliar humanidad y productividad. Tan
importante son las habilidades humanas como las técnicas. Una buena
técnica promueve relaciones basadas en la confianza. Kent Beck dice
que su terror a los deadlines desapareció cuando aprendió la siguiente
lección:

> "No es mi tarea gestionar las expectativas de otras personas. Es
> tarea de las otras personas manejar sus propias expectativas. Mi
> tarea es hacerlo lo mejor posible y comunicar claramente."

Lo peor que le puede pasar a un equipo de software es que el proyecto
en el que está trabajando se cancele y no se entregue después de haber
estado trabajando en él durante semanas. 

Las técnicas de XP persiguen dar confianza y seguridad y permitir que
nos sintamos satisfechos de nosotros mismos porque hemos dado lo mejor
para evitar que eso pase.


## Valores ##

En su libro _Extreme Programming Explained (Second edition)_ Kent
Beck expone la metodología usando el esquema tradicional de primero
formular los valores, después los principios, y después enumerar las
prácticas.

Los valores ayudan a guiar al equipo. Los valores recuerdan al equipo
por qué se hacen ciertas prácticas. Sin valores, un equipo puede caer
en el
[cargo-cult](https://en.wikipedia.org/wiki/Cargo_cult_programming),
por el que se realizan acciones de forma religiosa sin entender por
qué se hacen. 

Los valores que define son los siguientes:

- **Comunicación**: las prácticas de XP promueven comunicación abierta
	y honesta entre el equipo, gerencia y los clientes. Los equipos
	XP prefieren una comunicación abierta y transparente.

- **Simplicidad**: mantener el código y el diseño tan simple como sea
	posible incrementa la claridad, comprensibilidad, extensibilidad y
	mantenibilidad del sistema. Las soluciones simples a menudo
	requieren menos comunicación que las complejas. 
    
    En el contexto de XP, Kent Beck define un sistema simple como
    aquel que: 
    
    - Pasa todos los tests
    - Proporciona todas las funcionalidades
    - No tiene duplicación
    - Usa el mínimo número de clases y métodos

    <img src="imagenes/xp-cycles.png" width="300px" align="right"/>

- **Retroalimentación**: sin una retroalimentación continua y honesta
  todo se desmorona. La retroalimentación es lo que mantiene a todo el
  mundo en sintonía. Es lo que permite que los desarrolladores
  entreguen el sistema que el cliente realmente quiere. 
  
    En XP la retroalimentación aparece
    de muchas formas y en muchas escalas de tiempo. A nivel de minutos
    aparece cuando lanzamos los tests, después cuando hacemos pair
    programming, diariamente en las reuniones diarias o en cada
    iteración con la retroalimentación de los clientes.
  
- **Valentía**: Valentía es la acción efectiva frente al miedo. El
  miedo es algo que se sufre en el desarrollo de software. ¿Qué
  miedos pueden existir en el equipo de desarrollo?: 
  
    - Miedo a hacer algo mal, crear bugs. Sobre todo si estás
      escribiendo software que afecta a personas.  
    - Miedo a cambiar código, ya sea tuyo o de otros (código legacy o heredado).
    - Miedo a no poder terminar un proyecto en el que se ha invertido
      mucho trabajo (por ejemplo, un año) debido a que se cancele o a
      que nadie lo use. 

    La valentía se debe manifestar a veces en forma de acción,
	cuando conoces la solución a un problema. Otras veces en forma de
	paciencia. Si sabes que hay un problema pero no sabes cuál es, es
	necesario valentía para esperar a que el verdadero problema
	termine apareciendo. La valentía para decir la verdad, sea o no
	placentera, promueve la comunicación y la confianza. La valentía
	para descartar soluciones parciales y buscar otras nuevas promueve
	la simplicidad. La valentía por buscar respuestas reales y
	concretas crea retroalimentación. 

- **Respeto**: Los anteriores cuatro valores apuntan a uno subyacente:
  respeto. Si los miembros de un equipo no se preocupan de los otros,
  sobre lo que están haciendo, XP no funcionará. Si los miembros de un
  equipo no se preocupan sobre un proyecto, nada puede salvarlo. Nadie
  es intrínsecamente más valioso que ningún otro. Deben respetarse las
  contribuciones de todos. Yo soy importante y tú también. 

## Principios ##

<img src="imagenes/puente-principios-practicas.png" width="300px"
align="right"/>

Los principios guían al equipo a implementar los valores. Son ideas
más concretas que nos permiten escoger las mejores prácticas. Tanto
valores como principios justifican el por qué de las prácticas.

- **Humanidad**: Las prácticas que sigue un equipo deben satisfacer
  las necesidades humanas y proporcionar bienestar psicológico. Las
  necesidades que lista Beck son: seguridad básica, logro,
  pertenencia e intimidad. El equipo de desarrollo debe equilibrar las
  necesidades del individuo con las del equipo.

- **Economía**: Las prácticas que sigue el equipo debe balancear las
  necesidades de negocio con las técnicas. La gente que compra el
  producto es la que alimenta el negocio. El diseño y la entrega
  incremental permite al equipo entregar valor pronto y asegurar un
  valor económico al producto.

- **Beneficio mutuo**: Buscamos prácticas que beneficien a todas las
  partes en el momento presente. Una práctica que no beneficie al
  equipo ahora no es útil, por ejemplo escribir documentación para un
  futuro posible equipo de desarrollo. Las prácticas que dan beneficio
  mutuo nos ayudan ahora y en el futuro.

- **Auto-similitud**: Las prácticas que sigue un equipo pueden
  potencialmente adaptarse a diferentes contextos que comparten
  ciertas similitudes. Debemos intentar aplicar patrones conocidos a
  múltiples problemas.

- **Mejora**: Las prácticas que sigue un equipo evolucionan y mejoran
  a lo largo del tiempo. El objetivo de XP es la "excelencia en el
  desarrollo de software a través de la mejora". Es preferible empezar
  con algo imperfecto que esperar a la perfección.

- **Diversidad**: Las prácticas que sigue un equipo debería resolver
  los conflictos de forma productiva. "Dos ideas sobre un diseño
  representan una oportunidad, no un problema". La existencia de
  múltiples perspectivas proporcionan soluciones más ricas. El equipo
  se beneficia de una diversidad de habilidades, perspectivas,
  actitudes y experiencias.

- **Reflexión**: Las prácticas que sigue un equipo deberían permitir
reflexión a diferentes frecuencias y múltiples niveles. Los equipos
reflexionan sobre el cómo y el por qué del trabajo. Los equipos ven
los errores como una oportunidad de crecimiento.

- **Flujo**: Se deben reducir los tamaños de las trozos (de
  funcionalidad, de incremento, de código, etc.) para mejorar el
  flujo. "El flujo en el desarrollo de software consiste en entregar
  continuamente software de valor mediante la realización simultánea
  de todas las actividades del desarrollo". Los equipos quieren una
  corriente de trabajo que se mueve a través del sistema.

- **Oportunidad**: Los problemas son oportunidades de cambio. Un
  equipo que "juega seguro" hará menos errores pero también se moverá
  más lentamente de lo que se necesita.
  
- **Redundancia**: Las prácticas que sigue un equipo debería abordar
  problemas difíciles de varias formas. Por ejemplo, XP aborda el
  problema difícil de los defectos con "pair programming, integración
  continua, sentarse juntos, intervención real del cliente y
  despliegue diario.

- **Fallo**: Las prácticas que sigue un equipo deberían orientarlo
  hacia la acción. Cuando el equipo no sabe lo que hacer, debería
  intentar algo y obtener retroalimentación. "Si tienes problemas en
  tener éxito, falla". A veces es conveniente en lugar de largas
  conversaciones y debates realizar varios experimentos. Un fallo no
  es un desperdicio si me sirve para aprender algo.

- **Calidad**: Las prácticas que sigue un equipo deberían entregar
  productos de alta calidad. Las mejoras en la calidad "conducen a
  mejoras en otras propiedades deseadas como productividad y
  efectividad". No vas a ir más rápido aceptando rebajar la calidad.

- **Pequeños pasos**: Comienza con el cambio más pequeño e itera a
  partir de ahí. Descompón cambios grandes en pequeños cambios
  incrementales. "¿Qué es lo menos que puedes hacer que sea reconocible
  y que vaya en la dirección correcta?"

- **Responsabilidad aceptada**: Las prácticas que sigue un equipo
  debería empoderar a la gente que está trabajando en el problema con
  la autoridad para resolverlo. La responsabilidad es aceptada, no
  asignada. Deben evitarse las situaciones en las que la gente en una
  parte de la organización esté continuamente diciéndole a la otra lo
  que tiene que hacer.

## Prácticas ##

<img src="imagenes/practicas-xp.png" width="600px"/>

- El prefacio de la segunda edición de _Extreme Programming Explained_
  lo firma [Erich Gamma](https://en.wikipedia.org/wiki/Erich_Gamma)
  en 2004. **Erich Gamma** es uno de los _Gang Of Four_, autores del
  famoso libro _Design Patterns_. También es co-autor, junto con Beck,
  de **JUnit**. Y fue líder del equipo que desarrolló inicialmente el
  **proyecto Eclipse**, el popular IDE de desarrollo de Java.
  
  En este prefacio, Gamma comenta que **las prácticas XP son claves en
  el desarrollo de Eclipse**. Al ser un proyecto open source uno de los
  objetivos es realizar una desarrollo completamente transparente, ya
  que si no se sabe hacia dónde va el proyecto no es posible colaborar
  con él ni proporcionar retroalimentación.
  
  Las prácticas que utiliza Gamma en Eclipse son principalmente
  **refactoring**, **tests unitarios** y **feedback inmediato**:
  
  - **Pruebas desde el principio, frecuentes y automatizadas**: más de
    21,000 tests en el proyecto.
  - **Diseño incremental**: se avanza en el diseño día a día, con la
    restricción adicional de que es necesario mantener estable el API.
  - **Despliegue diario**: los componentes despliegan el código al
    menos una vez por día y se desarrolla sobre el código desplegado
    para obtener feedback inmediato y detectar pronto los problemas.
  - **Implicación del cliente**: la comunidad prueba continuamente los
    cambios y proporciona retroalimentación.
  - **Integración continua**: el código se compila y construye cada
    noche (_nightly build_). Una vez a la semana se hace una
    construcción de integración (_integration build_).
  - **Ciclos de desarrollo cortos**: algo más largos que los ciclos de
    una semana de XP. Cada seis semanas se entrega un
    _milestone_. El objetivo de cada milestone es mostrar el progreso
    y obtener feedback.
  - **Planificación incremental**: después de cada _release_ se
    realiza un borrador de plan de lo que se va evolucionar en el
    siguiente release. El plan se publica en la web pronto para que la
    comunidad pueda unirse al diálogo.

- Si tuviéramos que quedarnos con la enseñanza más importante de XP
sería,  sin lugar a dudas, el énfasis en las pruebas, y en concreto,
en la práctica de  TDD (Test Driven Development, desarrollo dirigido
por las pruebas). TDD consiste básicamente en invertir el desarrollo
habitual de los tests. No hacerlos después de escribir el código para
comprobar que no hay errores. Sino hacer el test antes de escribir el
código. Y escribir únicamente el código necesario para que el test
pase.

Esta idea tan simple en apariencia cambia radicalmente la forma de
enfrentarse al desarrollo. Lo veremos más adelante.

- Para XP las pruebas son el elemento fundamental del desarrollo, y
todos los desarrolladores deben escribirlas mientras que escriben el
código que finalmente irá a producción.

- Las pruebas se integran en un proceso de integración y construcción
continua lo que lleva a una plataforma muy estable para el desarrollo
futuro.

- Este énfasis en las pruebas como parte integral del desarrollo ha
sobrepasado a la propia XP y se ha incorporado en múltiples
metodologías y equipos de desarrollo (aunque no utilicen el resto de
prácticas XP). 

- Kent Beck es también una de las figuras claves de TDD, con sus libros y el
  software que ha desarrollado (jUnit). 

### 1. Sit Together ###

<img src="imagenes/open-space-spotify.png" width="500px"/>

- Un espacio abierto en el que todo el equipo pueda trabajar.
- Una forma de satisfacer la necesidad de espacio privado es limitando
el número de horas de trabajo.
- El espacio de trabajo debe promover que florezca la comunicación.
- Cuantas más reuniones cara-a-cara, más humano y productivo se
  convierte el proyecto. 

### 2. Whole Team ###

<img src="imagenes/cross-functional-team.png" width="500px"/>

- Sensación de equipo: todos somos equipo, estamos en esto juntos y
apoyamos el trabajo, el crecimiento y el aprendizaje de todos. 
- Los equipos son dinámicos, cuando disminuye el número de cambios en
  la BD el administrador ya no es necesario y puede dedicarse a otros
  proyectos.

### 3. Informative Workspace ###

<img src="imagenes/informative-workspace.png" width="500px"/>

- Hacer que el espacio de trabajo se empape del proyecto en el que
estamos trabajando. 
- Colocar las tarjetas con las historias en las paredes, agrupadas por
estado (más de esto cuando hablemos de Kanban). 
- Colocar también en un lugar visible distintas gráficas de evolución
  del proyecto. 

### 4. Energized Work ###

<img src="imagenes/pomodoro-technique.png" width="200px"/>

- Trabajar a pleno rendimiento, pero solo tantas horas como se pueda
ser productivo de forma sostenida.
- Con suficiente cafeína es muy fácil llegar al punto en el que el
código que se escribe quita valor al proyecto y (lo más peligroso) no
darse cuenta de ello.
- Es posible aumentar la productividad gestionando mejor el
tiempo. Por ejemplo, declarar una franja de dos horas como "Tiempo de
Programación", desconectar los e-mails y los móviles y dedicarse sólo
a eso.

- La técnica del Pomodoro es un ejemplo muy recomendable de
  utilización del trabajo energético. 
    - Libro interesante sobre la técnica del Pomodoro [Pomodoro Technique Ilustrated](https://pragprog.com/book/snfocus/pomodoro-technique-illustrated).
    - La idea original es de Francesco Cirillo. En [esta página](https://cirillocompany.de/pages/pomodoro-technique) anuncia
  sus cursos y se puede obtener su libro original.


### 5. Pair Programming ###

<img src="imagenes/pair-programming.png" width="300px"/>

<img src="imagenes/mob-programming.png" width="300px"/>

- Todo el código que va a producción debe ser  escrito con dos
personas sentadas frente a la  máquina.
- Pair programming es un diálogo entre dos personas  que están
simultáneamente analizando, diseñando,  probando e intentando
programar mejor. 
- Ventajas:
    - Se mantienen centrados mutuamente
    - Se clarifican ideas
    - Se vencen los bloqueos individuales
    - Se cumplen mejor los estándares del equipo
- Consejos:
    - Rotar las parejas
    - No juntar dos programadores novatos
    - No invadir el espacio personal del otro (monitores grandes)

- **Hablar de los dos roles distintos cuando se está haciendo pair programming.**

- Muy interesante el post [Pair
  programming](http://www.programania.net/desarrollo-agil/pair-programming/)
  de [Luis Artola](https://twitter.com/artolamola):
  - ¿Es más caro el desarrollo con pair programming? Su respuesta es
    que no. El **cuello de botella del desarrollo** no es teclear, es:
       - código poco expresivo difícil de entender
       - diseño no simple (complicado)
       - desconocimiento del dominio
       - cambiar cosas y volver a probarlo todo a mano (o no hacerlo y
         provocar nuevos fallos)

    Yo añadiría un par más, relacionados con problemas técnicos:
    
       - desconocimiento de las herramientas/frameworks/lenguajes con
         los que se trabaja
       - uso de herramientas/frameworks/lenguajes poco apropiados
       
  - La velocidad de desarrollo es cada vez menor: "Al principio voy
    rápido porque hay poco código y con un diseño cualquiera me
    vale. Pero cada vez me cuesta más añadir nuevas funcionalidades
    porque, además, no sé lo que estoy rompiendo.". Para evitar este
    problema es fundamental mantener un diseño simple. TDD y XP ayuda
    a ello.

  - Para que el pair programming resulte realmente eficaz:
    - Dos teclados y dos ratones (¡incluso dos pantallas!), dos sillas
      y la pantalla en medio. Hay que estar cómodo. También es muy
      útil tener a mano un ordenador auxiliar (portátil o tablet) en
      el que poder a veces buscar más información mientras que la otra
      persona programa.
    - Máxima intensidad: pomodoros, y un objetivo (troceado en un
      pequeño log de la sesión de pairing)
    - Máxima concentración: el que no escribe debe mantener la
      atención muy activa, por ejemplo llevando el log y aportando ideas
      todo el rato. Sino: ping pong (ver después).
    - Si un problema que nadie sabe resolver interrumpe la dinámica –>
      es mejor DEJAR DE PAIREAR y buscar la solución.

  -  Algunas malas costumbres:
     - Acceso poco equitativo a teclado o pantalla / dominio de una persona del teclado
     - Matrimonios: parejas que nunca cambian
     - Uno trabaja el otro descansa
     - Dos ordenadores
     - Cada uno hace “su propio trabajo”
     - Los debates duran más de diez minutos sin escribir código nuevo

  - Algunos buenos hábitos:
     - Descansar
     - Ser humilde y receptivo
     - Comunicarte y escuchar
     - Defender tu visión y saber ceder

- Patrón Ping pong (pair programming y TDD)
  - A escribe un test nuevo y lo ve fallar
  - B implementa el código para que el test pase
  - B escribe el nuevo test y lo ve fallar
  - A implementa el código para que el test pase 
  - Y así sucesivamente. El refactoring se hace cuando surge la
    necesidad por el que está escribiendo en ese momento.

- [Un entorno productivo en
  pareja](http://www.programania.net/diseno-de-software/un-entorno-productivo-en-pareja/),
  otro artículo de Luis Artola en el que explica con más detalle el
  entorno de trabajo para un proyecto concreto en el que usaron pair
  programming y añade algunas ideas más sobre cuándo hacer pairing y
  cuando no:
  
  - Hacemos pairing siempre que lo que nos impide avanzar es el
    conocimiento (ya sea técnico o de dominio).
  - Hacemos pairing siempre que se va a tomar una decisión de diseño
    importante en la que se va a basar el proyecto (cómo vamos a
    organizar los componentes, si se va a usar tal o cuál patrón,
    estrategia de testeo, etc…)
  - Siempre que hacemos pairing tenemos una lista preparada con el
    orden del día. Y sí: normalmente hacemos pairing de jornadas
    completas, preparando el entorno previamente para ser productivos
    y tener toda la información disponible y la posibilidad de tener
    discusiones productivas.
  - Es importante no hacer pairing cuando quieres asimilar algo que has aprendido.

### 6. Stories ###

<img src="imagenes/story.png" width="250px"/>

<img src="imagenes/user-story-card.png" width="400px"/>

- Escribir las historias en tarjetas pequeñas, indicando un nombre,
una  descripción y una estimación del tiempo. 
- Es más adecuado hablar de “historias” que de “requisitos” (palabra
con connotaciones de “inmutabilidad” y “permanencia” que no son
compatibles con “abrazar el cambio”). 
- Al estimar cada historia es fácil darse cuenta del coste de cada una
de ellas y podemos combinarlas, priorizarlas. 
- Colocar las tarjetas en la pared, en un sitio visible, no en un
  programa.
  
**Hablar de las tres Cs**

### 7. Weekly Cycle ###

<img src="imagenes/weekly-cycle.png" width="700px"/>

- Reunión al comienzo de cada semana:
    - Revisión del progreso hasta la fecha, incluyendo si el progreso
    de la semana previa se corresponde con lo previsto. 
    - Hacer que el cliente escoja historias que sumen una semana de tamaño para la semana actual
    - Fraccionar las historias en tareas, los miembros del equipo se
    apuntan a las tareas y las estiman. 

- Comenzar la semana escribiendo las pruebas automáticas que se
realizarán cuando las historias estén completas y pasar el resto de la
semana implementándolas e integrándolas en el proyecto 

- Al final de la semana las nuevas historias deben estar disponibles
  para ser desplegadas.

- La semana es un ciclo corto para poder hacer experimentos del estilo
  “vamos a usar la técnica del Pomodoro durante una semana” o “esta
  semana cambiamos de pareja cada hora”. 

### 8. Quarterly Cycle ###

- Es conveniente hacer reuniones con un ciclo superior al semanal para ver la evolución del proyecto en conjunto
- Cada 3 meses:
    - Identificar los cuellos de botella, especialmente los que no
      están controlados por el equipo.
    - Planificar el tema o los temas para el cuatrimestre.
    - Escoger historias que sumen un trimestre para cumplir con los
    temas escogidos. 
    - Centrarse en una visión general de cómo el proyecto encaja en la
    organización y del valor que añade. 
- Los trimestres también son un buen ciclo para reflexionar sobre el
  equipo y proponer y evaluar experimentos que duren más de una semana.

### 9. Slack ###

- Trabajar con un cierto colchón que suavice la tensión de cumplir
compromisos imposibles.
- Es importante establecer una atmósfera de confianza en la que los
que piden y los que desarrollan el producto se comunican de forma
clara y honesta.
- Trabajar con plazos no realistas introduce errores inmanejables,
mina la moral y construye relaciones antagonistas.
- Cumplir los compromisos, incluso modestos, elimina desperdicios
  (waste), suaviza las tensiones, mejora la credibilidad y construye
  unas relaciones basadas en la comunicación honesta. 

### 10. Ten-Minute Build ###

- Máximo de 10 minutos para construir automáticamente todo el sistema y ejecutar
todos los tests.
- Todo el proceso de build y de paso de las pruebas debería estar
automatizado.
- No comprobar sólo las pruebas de la nueva parte añadida al sistema, sino todas las anteriores.
- En continuous delivery se va un paso más allá y se automatiza
  también el despliegue y el lanzamiento de las nuevas funcionalidades
  en producción. 

### 11. Continuos Integration ###

<img src="imagenes/continous-delivery-pipeline.png" width="500px"/>

- No dejar pasar más de dos horas sin integrar los cambios que hemos
  programado. 
- La programación en equipo es un problema de “divide, vencerás e
integrarás”. 
- La integración es un paso no predecible que puede costar más que el
propio desarrollo.
- Integración síncrona: cada pareja después de un par de horas sube
sus cambios y espera a que se complete el build y se hayan pasado
todas las pruebas sin ningún problema de regresión.
- Integración asíncrona: cada noche se hace un build diario en el que
se construye la nueva versión del sistema. Si se producen errores se
notifica con alertas de mails o cambia de color una lámpara de lava. 
- El sistema resultante debe ser un sistema listo para lanzarse sin
  demasiados problemas. Si el objetivo es desplegar una web, hay que
  desplegar la web (en el entorno de staging).
  
### 12. Test-First Programming ###

Se denomina habitualmente a esta práctica Test Driven Design (TDD). Es
una de las prácticas más importantes de XP. Hablaremos más adelante
con mayor profundidad de esta técnica y haremos alguna
demostración. Veremos también un ejemplo en las prácticas.

La técnica se basa en escribir el código de forma iterativa, paso a
paso, y siempre comenzando por los tests. Supongamos que tenemos que
implementar una determinada funcionalidad. La analizamos y pensamos en
cómo implementarla, dividiéndola en pequeños elementos necesarios para
poder completarla. Escribimos estos elementos en una lista y empezamos
a codificarlos utilizando el siguiente ciclo:

1. Se escribe un único test en el que se especifica un pequeño
   incremento de funcionalidad que el código debe realizar, un ejemplo
   de lo que el código debe hacer en forma de test. Se añade el test a
   los ya existentes y se lanzan todos. El test que acabamos de añadir
   falla (rojo).
2. Se escribe únicamente el código necesario que hace que el test
   pase (verde).
3. Ahora que tenemos una base de tests que funciona perfectamente, se
   analiza el código y los tests, se detectan problemas de diseño y se
   realiza una refactorización (profundizaremos más adelante
   en esto). Se vuelven a lanzar los tests para asegurarnos
   que la refactorización no ha roto nada.

<img src="imagenes/tdd.png" width="500px"/>

Se repite el ciclo, cada vez añadiendo nuevos tests que vayan
acercando el código a la nueva funcionalidad. En el proceso de añadir
pequeños tests y ampliar el código, nos iremos dando cuenta de cosas
que hay que implementar y que no habíamos tenido en cuenta. Las
anotamos en la lista de tareas a hacer y en algún momento tocará
resolverlas con el ciclo de TDD.

Los tests y el código que generan deben ser muy pequeños y
concretos. Sólo se generalizará cuando se detecte que sea
necesario. Se hará en la fase de refactorización. 

Es importante que los tests vayan haciendo crecer la funcionalidad en
pequeños incrementos. Al ser los cambios pequeños hay menos
posibilidades de estropear cosas.

En TDD se utiliza un enfoque _bottom-up_: primero se programan los
elementos y funcionalidades básicas y después se van programando
funcionalidades de mayor nivel que se basan en las anteriores.

En TDD no nos preocupamos demasiado de que los tests sean unitarios ni
de usar mocks para aislar funcionalidades. Como la batería de tests se
construye de forma incremental, cuando hacemos los tests de más alto
nivel no hace falta aislar los elementos de bajo nivel porque ya hemos
comprobado que funcionan correctamente.

En ocasiones sí que se usarán mocks por motivos de eficiencia y para
que los tests pasen más rápido. Sobre todo en los casos de tests de
integración en los que hay que conectar con servicios externos.

Utilizando esta técnica las pruebas no sólo sirven para comprobar que
el software funciona correctamente, sino que sirven para especificarlo
y diseñarlo.

La utilización de TDD tiene muchas ventajas:

- En todo momento tenemos una especificación clara de lo que nuestro
  código tiene que hacer.
- Cohesión y acoplamiento - si es difícil escribir el test,  es una
señal de que tenemos un problema de  diseño. El código débilmente
acoplado y altamente  cohesionado es más fácil de probar.
- Confianza: escribiendo código limpio que funciona y  demostrando tus
intenciones con las pruebas construye una relación de confianza con
tus compañeros.
- Ritmo: es muy fácil perderse durante horas cuando se está
programando. Con el enfoque de test-first, está claro lo que hay que
hacer a continuación: o escribimos una prueba o hacemos que funcione
una prueba  rota (broken test). El ciclo que se genera se convierte
pronto en algo natural y eficiente: test, code, refactor, test, code,
refactor


### 13. Incremental Design ###

<img src="imagenes/evolutive-process.png" width="400px"/>

- Diseño gradual, con pasos pequeños y seguros.
- El diseño no debe hacerse sólo al principio, sino conforme vamos
  adquiriendo experiencia. 
- Invertir cada día en el diseño del sistema, luchando por ver cómo la
  parte que estamos construyendo puede mejorarlo en su conjunto.
- Pensar todo el tiempo en el problema en conjunto, buscando formas de
  diseñar mejor todo el sistema. Cuando tengamos claro un diseño
  mejor, trabajar gradual pero continuamente para alinear el sistema
  real con este diseño. 
- Los equipos XP trabajan duro para crear las condiciones bajo las que
  el coste de cambiar el software sea bajo.
- Una regla sencilla para mejorar el diseño: eliminar la duplicación. 

**Hablar algo más de deuda técnica**


### Prácticas secundarias ###

Team

- Real Customer Involvement
- Team Continuity
- Shrinking Teams 

Programming

- Shared Code 
- Code and Test
- Single Code Base

Business

- Root-Cause Analysis 
- Negotiated Scope Contract
- Pay-Per-Use

Deliverying

- Incremental Deployment 
- Daily Deployment


## Referencias ##

- Ward Cunningham y otros, [Páginas de WikiWiki sobre Extreme Programming](http://wiki.c2.com/?ExtremeProgrammingRoadmap)
- Kent Beck (2004) [_Extreme Programming Explained: Embracing Change (Second
  Edition)_](https://learning.oreilly.com/library/view/extreme-programming-explained/0321278658/)