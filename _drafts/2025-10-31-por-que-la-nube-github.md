---
layout: post
title: "💻 Optimizando tu Web Estática: Por qué la Nube es tu Mejor Aliada para Imágenes (Adiós, Límites de GitHub)"
---



Si utilizas GitHub Pages para alojar tu sitio estático (como el que construimos en Stairway) estás aprovechando una herramienta fantástica y gratuita. Sin embargo, para mantener esa eficiencia y evitar costos inesperados, hay una regla de oro que siempre aplicamos: ¡saca las imágenes del repositorio!

En Stairway, recomendamos y usamos Cloudinary para alojar todo nuestro contenido multimedia. Aquí te explicamos por qué es el flujo de trabajo superior para cualquier proyecto serio.

1. El Costo Oculto de las Imágenes en GitHub
GitHub Pages es una maravilla, pero la versión gratuita tiene límites estrictos que puedes alcanzar muy rápido si subes tus imágenes directamente a tu repositorio (incluso usando la funcionalidad LFS, que tiene sus propios límites de datos).

Característica	Límite de la Versión Gratuita de GitHub
Tamaño del Repositorio	1 GB (se recomienda mantenerlo por debajo de 1 GB para un mejor rendimiento)
Ancho de Banda	100 GB por mes
Archivos (Páginas)	10 builds por hora

El gran peligro es el límite de 1 GB por repositorio. Unos cuantos archivos PDF grandes, imágenes de alta resolución o vídeos cortos pueden hacer que tu proyecto supere ese límite rápidamente, obligándote a migrar o, en el peor de los casos, a pagar una suscripción para acceder a funciones que te permitan manejar repositorios más grandes.

✅ Cómo Verificar si Estás Cerca del Límite
Para evitar sorpresas, debes revisar el tamaño de tu repositorio.

Ve a la página principal de tu repositorio en GitHub.

Busca la sección de información (normalmente en la parte superior derecha, debajo de la descripción).

Ahí verás el tamaño actual del repositorio, por ejemplo: "256 MB".

Si tienes varios sitios estáticos, la suma total de todos tus repositorios es lo que debes monitorear para una gestión eficiente de recursos.

2. El Flujo de Trabajo Inteligente: GitHub Pages + Cloudinary
En Stairway diseñamos páginas estáticas con este flujo de trabajo respecto a la multimedia: GitHub se encarga del código estático (HTML, CSS, JS) y Cloudinary se encarga de la multimedia.


Ventaja	Descripción
Estaticidad Pura	Tu repositorio se mantiene ligero y 100% estático. No hay archivos multimedia pesados. Esto garantiza que tus builds sean veloces y que nunca te acerques al límite de 1 GB de GitHub.
Optimización Automática	Cloudinary es más que un almacenamiento. Optimiza y comprime las imágenes automáticamente. Puedes usar su URL pública para redimensionar, recortar o cambiar el formato al vuelo (por ejemplo, convertir una imagen a WebP para navegadores modernos), ¡todo sin tocar el archivo fuente!
Seguridad y Costo	Al usar la URL pública que te da Cloudinary, puedes incrustar la imagen en tu código Jekyll sin peligro. Es una URL de entrega de contenido (CDN), no una clave de acceso. Esto te permite aprovechar el nivel gratuito de Cloudinary para la mayoría de los sitios pequeños y medianos, posponiendo por mucho tiempo la necesidad de pagar más en GitHub.

En resumen: Usar un servicio externo como Cloudinary te permite mantener tu sitio estático, sin peligros, y asegurarte de que la versión gratuita de GitHub Pages dure lo máximo posible, mientras ofreces una experiencia multimedia más rápida y optimizada a tus usuarios.

❓ Pregunta Extra: ¿Cloudinary solo es para Imágenes?
¡No! Cloudinary es un servicio de gestión de activos digitales muy completo.

Imágenes y Vídeos: Es su punto fuerte, con optimización y transformación automáticas.

PDFs (Documentos): Sí, Cloudinary te permite subir y gestionar archivos PDF. De hecho, tiene la ventaja de que puede renderizar la primera página del PDF como una imagen automáticamente, lo cual es excelente para crear miniaturas de documentos.

Nuestra Recomendación en Stairway: Para documentos que requieran una simple descarga y no necesiten transformación (como un informe o un manual), usar un servicio de almacenamiento en la nube dedicado (como Google Drive, Dropbox o S3) podría ser más sencillo de gestionar. Sin embargo, si quieres optimizar o previsualizar el PDF de forma avanzada, Cloudinary es la herramienta superior.

En resumen: Usar un servicio externo como Cloudinary te permite mantener tu sitio estático, sin peligros, y asegurarte de que la versión gratuita de GitHub Pages dure lo máximo posible, mientras ofreces una experiencia multimedia más rápida y optimizada a tus usuarios.

❓ Pregunta Extra: ¿Cloudinary solo es para Imágenes?
¡No! Cloudinary es un servicio de gestión de activos digitales muy completo.

Imágenes y Vídeos: Es su punto fuerte, con optimización y transformación automáticas.

PDFs (Documentos): Sí, Cloudinary te permite subir y gestionar archivos PDF. De hecho, tiene la ventaja de que puede renderizar la primera página del PDF como una imagen automáticamente, lo cual es excelente para crear miniaturas de documentos.

Nuestra Recomendación en Stairway: Para documentos que requieran una simple descarga y no necesiten transformación (como un informe o un manual), usar un servicio de almacenamiento en la nube dedicado (como Google Drive, Dropbox o S3) podría ser más sencillo de gestionar. Sin embargo, si quieres optimizar o previsualizar el PDF de forma avanzada, Cloudinary es la herramienta superior.
