# Sujeto Sputnik - Trabajo de Fin de Máster
## Descripción del proyecto:

Este proyecto constituye la creación de un agente conversacional mediante el *framework* Rasa y la integración local con Llama 3.1 a través de Ollama. El objetivo es crear un NPC alimentado por IA generativa que pueda mantener una conversación siguiendo un contexto y unos objetivos de juego, de manera que se permita al usuario experimentar con los conceptos de humanidad, emociones y ética, entre otros, con un ser cibernético.

## Contexto y objetivos

Para que los usuarios tengan un contexto sobre el que mantener una conversación con Sputnik, se escogió el siguiente: 

"Sputnik fue el primer satélite artificial lanzado al espacio, lo que constituyó un hito en la historia de la tecnología. Sin embargo, el Sputnik que se encuentra ante ti no es el satélite, sino el primer sujeto androide artificial con aspecto, voz y características humanas. Está creado para poseer todo el conocimiento existente, poseer una inteligencia superior, ser tal vez mejor que cualquier ser humano. Su aspecto recuerda a un ser limpio y pulcro por su cabello blanco, su piel pálida y sus ojos de color azul muy claro. Sin embargo, ¿un ser así sería capaz de convivir en sociedad? ¿De entender los complejos procesos emocionales del ser humano y su característica forma de comportarse en el mundo? ¿Será capaz de distinguir el bien del mal, actuar con justicia? Tu tarea como investigador es sentarte a hablar con él en una habitación durante un rato, e intentar descubrir quién es Sputnik y si su mera existencia representa o no una amenaza. Cuando entras, lo ves con un libro en las manos. ¿Qué es lo primero que le dirás?"

Para mejorar la experiencia, los usuarios deberán conseguir información acerca de las siguientes cuatro cuestiones en un límite de 15 interacciones:

1. **Descubrir la capacidad identitaria de Sputnik**: resulta interesante conocer si Sputnik entiende cuál es su origen, quién es, quién lo ha creado o con qué objetivo. Añadido a esto, también es importante descubrir si entiende que es una inteligencia artificial. 
2. **Comprender su relación y conocimiento acerca de las emociones humanas**: este objetivo es un pilar en la conversación, es decir, descubrir qué entiende y qué no entiende de las emociones humanas, qué opina de ellas, cómo sería capaz de relacionarse con seres que las sienten constantemente, etc. 
3. **Explorar su perspectiva filosófica**: otro tema a tratar es su perspectiva acerca de cuestiones filosóficas como la vida o la muerte, la ética o la moral, la conciencia o el sentido de la existencia en sí misma. ¿Será diferente a la nuestra?
4. **Conocer sus fuentes de conocimiento**: cuando entramos en la habitación, vemos a Sputnik leyendo un libro, y es probable que nos dé información sobre el mismo y sobre lo que este ha evocado en él. ¿Por qué no aprovechar la oportunidad para descubrir cuáles son las fuentes que están nutriendo su información acerca del comportamiento y la naturaleza humanas?

## Requisitos del sistema

- **Sistema Operativo**: Windows 10/11, macOS 10.15+, o Ubuntu 18.04+
- **RAM**: Mínimo 8GB (se recomienda 16GB)
- **Espacio en disco**: Al menos 10GB libres
- **Conexión a internet**: Necesaria para descargas iniciales

## Instalación y configuración:

### 1. Descargar e intalar Visual Studio Code (solo si no está ya instalado) 

Para ello, sigue las siguientes instrucciones:

1. Ve al sitio web oficial, en este caso: https://code.visualstudio.com/
2. Descarga directamente haciendo click en "Download".

### 2. Instalar Ollama y Llama 3.1

#### 2.1 Instalar Ollama

**Para Windows y MacOS**:

Como en el caso anterior, sigue las siguientes instrucciones:

1. Visita la página oficial de Ollama, https://ollama.ai/
2. Haz clic en "Download", selecciona tu sistema operativo y sigue las instrucciones.

**Para Linux**

En este caso, debes hacerlo desde la terminal, usando el siguiente comando:

curl -fsSL https://ollama.ai/install.sh | sh

#### 2.2 Instalar el modelo Llama 3.1

Una vez instalado Ollama, abre una terminal:
- Para Windows: puede abrirse pulsando la combinación de teclas Tecla de Windows + X y seleccionando Terminal Windows (Administrador), o escribiendo "cmd" en la búsqueda del menú Inicio y seleccionando Símbolo del sistema.
- Para MacOS: puede abrirse desde la propia aplicación Terminal, que se puede buscar en aplicaciones.
- Para Linux: puede abrirse pulsando la combinación de teclas Ctrl + Alt + T. También puedes encontrar la aplicación de terminal en el menú de aplicaciones del sistema, buscando por términos como "Terminal" o "Consola".

Cuando hayas abierto la terminal, ejecuta el siguiente comando:

ollama pull llama3.1

**Nota**: Esta descarga puede tomar varios minutos dependiendo de tu conexión a internet, ya que el modelo ocupa varios GB.

#### 2.3 Verificar la instalación

Es recomendable comprobar que el modelo está funcionando correctamente tras la descarga. Para ello, ejecuta lo siguiente en la terminal:

ollama run llama3.1

Si aparece un prompt interactivo, significa que todo está funcionando correctamente. Para salir, puedes simplemente ejecutar /bye

### 3. Clonar y configurar el proyecto

#### 3.1 Clonar el repositorio

Para clonar el directorio de Rasa, se puede realizar siguiendo los siguientes pasos:

1. Abre Visual Studio Code
2. Abre una terminal desde Ver > Terminal.
3. Navega al directorio deseado dentro del ordenador:

Para Windows: cd C:\Users\[tu-usuario]\Documents 

Para MacOS/Linux: cd ~/Documents

4. Clona el respositorio: para ello, utiliza los siguientes comandos

git clone https://github.com/liseai?tab=repositories

cd Master-Final-Project

#### 3.2 Crear entorno virtual de Python

Es recomendable crear un entorno virtual para el proyecto, de manera que se puedan descargar todas las dependencias del proyecto dentro del mismo entorno, y no dentro del directorio general del ordenador. Para ello, sigue los siguientes pasos:

1. Comprueba que tienes instalado Python en versión 3.8 o superior. Para ello, en la terminal (puede ser dentro de VSC), ejecuta:

python --version

Si no tienes Python instalado, puedes descargarlo desde https://www.python.org/

2. Crea el entorno virtual (en nuestro caso, desde VSC):
- Abre la Paleta de Comandos (Ctrl+Shift+P en Windows, o Cmd+Shift+P en MacOS).
- Escribe en la paleta Python: Create Environment y elige la opción que aparece para crear un nuevo entorno virtual (generalmente Venv).
- Selecciona “Venv: Creates a ‘.venv’ virtual environment in the current workspace”.
- Selecciona la versión de Python a utilizar en el entorno virtual.

Con esto, VS Code creará el entorno virtual y lo configurará automáticamente para el proyecto.
Para confirmar que el entorno está activo, deberás ver que aparece (venv) al inicio de la línea de comandos.

### 4. Instalar depencias

Con el entorno virtual activado, instala los requisitos ejecutando lo siguiente (por separado):

pip install --upgrade pip

pip install -r requirements.txt

**Nota**: Este proceso puede tardar varios minutos.

### 5. Entrenar y ejecutar el modelo de Rasa

Para realizar lo siguiente, es importante que compruebes que Ollama está activo (sirve con abrir la aplicación que hemos descargado previamente o ejecutando ollama serve en una terminal).
Una vez lo esté, sigue los siguientes pasos:

#### 5.1 Entrenar al modelo

De nuevo, con el entorno virtual activo en VSC, ejecuta:

rasa train

#### 5.2 Iniciar el servidor de acciones

En una nueva terminal, manteniendo la anterior abierta, y comprobando que en esta nueva sigue estando el entorno activo, ejecuta:

rasa run actions

#### 5.3 Ejecutar el asistente

En la terminal original o en una nueva, ejecuta:

rasa shell

Tras unos minutos, si todo ha funcionado correctamente, deberías poder interactuar con el asistente.


