---
layout: post
title: "Ajustar un objeto o capa al tamaño del lienzo y viceversa en GIMP 🎨"
meta_description: 🎨 Escala capas y objetos en GIMP para que ocupen todo el lienzo. Aprende a usar la herramienta Escala (Shift + T) y la función de Recortar contenido para ajustar tus imágenes de forma precisa.
---

Esta guía te ayudará a escalar un objeto o imagen para que **ocupe todo el lienzo** (área de trabajo) de tu proyecto en GIMP.

---

## ⚙️ Requisitos Previos (Selección de Capa)

Antes de empezar, el elemento que quieres escalar debe estar en una **capa independiente**.

1.  Asegúrate de que la capa deseada esté activa haciendo clic sobre ella en el **Panel de Capas** (normalmente situado a la derecha).
2.  Si tu elemento está en un canal alfa, asegúrate de **convertir el canal alfa a una selección** antes de usar la herramienta de escala.

---

## Paso 1: Acceder a la Herramienta Escala

Una vez que la capa esté seleccionada, inicia la herramienta de transformación:

* **Menú Principal:**
    > Herramientas &gt; Herramientas de Transformación &gt; **Escala**
* **Atajo de Teclado:**
    > **Shift + T**

Al activarla, aparecerá un cuadro con manejadores ajustables (cuadritos) alrededor del objeto seleccionado.

---

## Paso 📐 Paso 2: Definir y Ajustar el Tamaño

El objeto se seleccionará con un cuadro con los vértices y aristas ajustables.

1.  **Mantener Proporciones:** En la ventana de diálogo de la herramienta Escala, asegúrate que el **ícono de la cadena** entre los campos de **Ancho (Width)** y **Alto (Height)** esté **cerrado**. Esto es crucial para evitar deformar la imagen.
2.  **Verificar Lienzo:** Verifica las dimensiones de tu lienzo (Menú Principal &gt; Imagen &gt; Tamaño del lienzo...).
3.  **Ajustar Medidas:** Introduce las medidas deseadas para el **Ancho** y **Alto** de la capa, haciendo que coincidan con las dimensiones de tu lienzo.

> 💡 **Consejo para Proporciones:** Si quieres mantener la proporción original de la imagen, solo introduce la medida más grande (Ancho o Alto). GIMP calculará automáticamente el otro valor si el ícono de la cadena está cerrado.

---

## Paso 3: Aplicar la Transformación

1.  Una vez que las dimensiones son correctas y se ajustan a tu lienzo, haz clic en el botón **Escalar (Scale)** en la ventana de diálogo.

Tu elemento se habrá agrandado y ocupará todo el espacio del lienzo, completando la "página" de tu proyecto.

------

## ✂️ Caso Inverso: Ajustar el Lienzo a la Imagen

Si lo que deseas es lo contrario —que el lienzo se ajuste a los límites de la capa o imagen visible, eliminando el espacio vacío— puedes usar esta opción rápida:

Menú Principal:

Imagen > Recortar contenido (Crop to Content)

Al instante, el área de trabajo (lienzo) se reducirá para ajustarse perfectamente a los límites de las capas visibles en tu proyecto.
