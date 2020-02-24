
# Módulo 1 - Evaluación final

Ejercicio en SASS de Beatriz Pérez para la evaluación final del módulo 1 de Adalab.

Estructura de ramas del repositorio:
    1. stable - última versión de código para producción. Se fusionarán los cambios desde master una vez ésta sea estable.
    2. master - rama principal en que se fusionan los cambios realizados en las distintas ramas de desarrollo.
    3. feat/accessibility - rama de desarrollo para características de accesibilidad. Los cambios se volcarán en master.
    4. feat/hidden-header - rama de desarrollo para características del header. Los cambios se volcarán en master.


Definición del sistema de diseño:

Estructura HTML:

    Documentos
        1. index.html con metainformación, links a hojas de estilos (fuentes de google y main.css)y un contenedor de página (page) en el que se incluyen llamadas a los partials de cada sección.
        2. partials html para cada una de las secciones.

    Elementos:

        a. en index.html:
            1. contenedor de documento:
                page
            2. llamadas a cada uno de los html partials.

        b. en los html partials de cada sección:
            1. contenedores de página que permiten situar y asignar colores e imágenes de fondo a cada sección:
                sección (semántica) con clase: container__page--"nombre de seccion"
                e id para enlaces a sección: "nombre de seccion"
            2. contenedores generales que permiten asignar padding o margin al conjunto:
                div con clase: container__general
            3. contenedores de sección que permiten aplicar propiedades para la maquetación como display:
                div con clase: container__section--"nombre de seccion"
            4. elementos propios de cada sección, con estilos asignados mediante:
                    · clase BEM+camelCase para estilos en partials de layout (si son necesarios) 
                            "nombre de seccion"__"element"--"modifier"
                    · clase BEM+camelCase para estilos de botón (si se trata de un botón predefinido)
                            button__"element"--"modifier"
                    · clase BEM+camelCase para estilos tipográficos (si hay un contenido de texto)
                            text__"nombre de seccion"--"modifier"


Estructura CSS:

    a. un main.scss qu incluye:
        1. imports de scss para standards establecidos (core), componentes (components) y estilos de página y sección (layout).

    b. una carpeta core que incluye:
        1. reset.scss con "normalize.css v8.0.1", definición de modelo de caja y eliminación de márgenes y paddings. Además, eliminación de decoración de listas y enlaces.
        2. variables.scss con definición de variables de colores, fuentes y colores de fuente.
        3. mixins.scss con bloques de código para estilos recurrentes como el centrado de elementos.

    c. una carpeta components que incluye:
        1. typography.scss con los estilos asignados a títulos, textos y textos de componentes.
        2. buttons.scss con los estilos asignados a cada tipo de botón.

    d. una carpeta layout que incluye:
        1. archivo structure.scss con los estilos del container__general que asignan tamaño(100% de su contenedor) y padding al conjunto: .container__general
        2. un archivo scss por sección, que incluye:
            - tamaño y fondo de la sección: .container__page--"nombre de seccion"
            - tamaño y estilos de maquetación de la sección: .container__section--"nombre de seccion"
                    · ajuste de tamaño al 100% de su contenedor.
                    · padding vertical.
                    . sistema de maquetación (display) y sus propiedades derivadas.
            - estilos de los elementos propios de cada sección.
            
