
User
oye si uno usa pelican o fastapi o algo asi o django, entodos uno puede usar la ia de google?
Model
ThinkingThoughts
Expand to view model thoughts

chevron_right
¡Sí, absolutamente! De hecho, es incluso más fácil en esos frameworks que en Jekyll.
La razón es simple: todos los frameworks que mencionaste (Pelican, FastAPI, Django) están escritos en Python, y Python es el "lenguaje nativo" de la Inteligencia Artificial hoy en día. Google ofrece librerías oficiales (SDKs) diseñadas específicamente para Python.
Aquí te explico cómo funcionaría la integración en cada uno, porque el enfoque cambia un poco dependiendo de si es un sitio estático o dinámico:
1. ¿Cómo se conecta? (Lo básico)
Independientemente del framework, la "magia" ocurre instalando la librería oficial de Google:
code
Bash
pip install google-generativeai
Y el código base siempre es algo así:
code
Python
import google.generativeai as genai

genai.configure(api_key="TU_API_KEY_AQUI")
model = genai.GenerativeModel('gemini-1.5-flash') # O el modelo que prefieras

respuesta = model.generate_content("Escribe un resumen sobre impuestos en Chile")
print(respuesta.text)
2. Integración según el Framework
A. FastAPI y Django (Sitios Dinámicos / Apps)
En estos casos, la IA responde "en vivo" a lo que hace el usuario.
Django: Puedes crear una "Vista" (View) que reciba un texto de un formulario, se lo envíe a Gemini (la IA de Google), y guarde la respuesta en tu base de datos o se la muestre al usuario.
Ejemplo: Un chatbot de soporte técnico para tu empresa o un generador de descripciones de productos automático en tu admin.
FastAPI: Es ideal para crear una API que sirva como "puente". Tu frontend (React, Vue, o una App móvil) le pide algo a tu FastAPI, y tu FastAPI le pregunta a Google y devuelve la respuesta en milisegundos. Es muy rápido y eficiente para esto.
B. Pelican (Sitio Estático)
Pelican es el equivalente a Jekyll pero en Python. Aquí la integración es diferente porque no hay un servidor ejecutándose todo el tiempo. La IA se usa durante la generación (build) del sitio.
Automatización de contenido: Puedes escribir un plugin pequeño en Python (o un script pre-build) que:
Lea tus artículos en Markdown.
Se los envíe a la IA de Google para que genere automáticamente el resumen, las etiquetas (tags), o traduzca el artículo a inglés.
Inserte eso en el HTML final.
Ventaja: Solo gastas cuota de API cuando "compilas" tu sitio, no cada vez que alguien lo visita.
3. ¿Por qué conviene más Python que Jekyll para esto?
Si bien en Jekyll (Ruby) se puede usar la IA, generalmente tienes que hacer llamadas curl o buscar librerías de la comunidad que a veces están desactualizadas.
En Django/FastAPI/Pelican, al ser Python, tienes:
Soporte oficial: Google actualiza la librería de Python el mismo día que lanza nuevas funciones.
Facilidad: Manejar los datos (JSON, texto) es nativo y muy sencillo.
Herramientas extra: Puedes usar herramientas como LangChain (que es para encadenar procesos de IA complejos) que funcionan nativamente en Python.
Resumen
Si estás pensando en migrar de Jekyll a Pelican (para seguir con sitios estáticos) o a Django/FastAPI (para hacer apps web), integrar la IA de Google (Gemini) será cuestión de agregar unas 5 a 10 líneas de código.
Model
ThinkingThoughts
Expand to view model thoughts

chevron_right
