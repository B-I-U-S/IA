# Descripción del proyecto

Este proyecto busca convertirse en un punto de partida accesible para cualquier persona interesada en el fascinante mundo de los chatbots y los modelos de lenguaje extenso (LLMs). Nuestro objetivo es proporcionar una base sólida de conocimientos y herramientas prácticas que permitan a usuarios de todos los niveles, desde principiantes hasta desarrolladores experimentados, adentrarse en la creación de sus propios chatbots. Queremos democratizar el acceso a esta tecnología y fomentar la innovación en el campo de la interacción humano-máquina.

# Pasos para la puesta en marcha

## Arrancar LLM(Large Language Model)

El primer paso en nuestro proyecto, procedemos a inicializar el modelo de lenguaje LLM(Large Language Model) que servirá como base para nuestro chatbot. En este caso, hemos seleccionado Llama 3.2 3B, un modelo de última generación conocido por su capacidad para generar texto de alta calidad. Para facilitar su implementación y gestión, decidimos ejecutar Llama 3.2 3B a través de un contenedor Docker utilizando la plataforma Cortex. Esta elección nos permite aislar el entorno de ejecución del LLM, garantizando una mayor estabilidad y portabilidad del proyecto y ejecutarlo usando la GPU o CPU.

```
# Arrancamos el contenendor usando la CPU
docker run -it -d --name cortex -p 39281:39281 menloltd/cortex

#  O alternativamente, usando la GPU requiere los drivers 'nvidia-docker' y evidentemente el hardware adecuado
docker run --gpus all -it -d --name cortex -p 39281:39281 menloltd/cortex

# Descargamos el modelo y lo arrancamos 
docker exec -it cortex cortex run llama3.2:3b-gguf-q4-km
```

## Puesta en marcha del chatbot

Para arrancar el chatbot simplemente debemos instalarlas dependencias del python y arrancar el script 'main.py'(En nuestro caso vamos a crear también un entorno virtual de Python con el objetivo de tener un único espacio con las dependencias de nuestro proyecto):

```
# Creación y activación del virtual env
virtualenv env
source env/bin/activate

# Instalaciión de dependencias
pip install -r requirements.txt

# Arranque del script
python main.py
```

# Material complementario

- Vídeo de Youtube ["Aprende a desarrollar chatbots desde 0"](https://www.youtube.com/watch?v=Q_NLkUsJJ2c)
- Artículo ["Cortex: Desplegando LLMs en local"](https://www.albertcoronado.com/2024/12/03/cortex-plataforma-de-ia-para-desplegar-llms-en-local) 



