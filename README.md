# llm_JFAG
Repositorio para implementar LLM 

## 1.instalación 

como primer paso descargamos ollama desde su página web [ollama](https://ollama.com/download/linux) de su página web y esperamo ejecutamos el siguiente Colorad comando:

````bash
$ curl -fsSL https://ollama.com/install.sh | sh
````

## 2.ejecutar el servidor 
ejecutar el servidor de api rest de ollama con el siguiente comando

````bash
$ ollama serve
````

## 3.descargar un modelo 

en la página de ollamab descarga un modelo [modelo](https://ollama.com/library) utilizando el siguiente comando:

````bash
$ ollama pull tinyllama
````

## 4.ver API REST en modo streaming
para ver APIS en ollama en modo streaming para para que lo vaya generando se usa el siguiente comando:
"La parte de salida.md es para guardar lo que genera el comando ".
````bash
curl http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
    "prompt": "Why is the sky blue?"
    }' -o salida.md
````
## 4.1 Para verlo en modo no streaming 
para ver las API en modo no streaming osea,que lo genere de un totazo se usa El siguiente comando:git commit -m "UPDATED README.md"

````bash
curl http://localhost:11434/api/generate -d '{
  "model": "tinyllama",
    "prompt": "Why is the sky blue?",
      "stream": false
      }'
````

## 5. para guardar en GitHub
Para actualizar en GitHub se puede de 3 maneras:

Prepara el archivo README.md para ser incluido en la siguiente versión del proyecto.
````bash
git add README.md
````

Crea una nueva versión del proyecto, incluyendo los cambios del archivo README.md y añadiendo un mensaje descriptivo.
````bash
git commit -m "UPDATED README.md"
````
Envía la nueva versión del proyecto (con los cambios) al repositorio remoto en GitHub, específicamente a la rama principal llamada main
````bash
git push origin main
````
````bash
git push -u origin main$ curl -fsSL https://ollama.com/install.sh |sh
````


## 6.Consultar a groq

Estructura basica para realizar una consulta con Groq mediante su API REST 

````bash
curl "https://api.groq.com/openai/v1/chat/completions" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer ${GROQ_API_KEY}" \
  -d '{
         "messages": [
           {
             "role": "user",
             "content": "¿Por que el cielo es azul?"
           }
         ],
         "model": "llama3-8b-8192",
         "stream": false,
       }'
  ````

  ## 7. Ejecutar codigo en python

  Estructura ejemplo:
 ````bash 
  import requests

url = 'http://localhost:11434/api/generate'
myobj = {
    'model': 'tinyllama',
    'prompt': 'Why is the sky blue?',
    'stream': False
}

x = requests.post(url, json = myobj)

print(x.text)
````

Codigo para ejecutar el codigo:

  ````bash
 python3 00_app.py
````