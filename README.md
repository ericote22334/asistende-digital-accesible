# 🍳 Cocina Escuela – Actividad de programación (HTML y CSS)

Tres sistemas simples para trabajar con alumnos de 4to año. Están hechos **solo con HTML y CSS** (sin JavaScript) y con código básico, para poder "despedazarlos" y que los alumnos completen los bloques que faltan.

## 📁 Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Pantalla de inicio para elegir el sistema |
| `equipo1_recetario.html` | **Equipo 1:** Módulo Recetario Visual |
| `equipo2_herramientas.html` | **Equipo 2:** Módulo Herramientas y Seguridad en Cocina |
| `equipo3_comandera.html` | **Equipo 3:** Módulo Comandera / Pedidos del Día |

> ⚠️ Los 4 archivos tienen que estar **en la misma carpeta**, porque se enlazan entre sí.

## ▶️ Cómo abrirlo

1. Guardar los 4 archivos en una misma carpeta.
2. Hacer doble clic en `index.html` (se abre en el navegador).
3. Elegir un sistema. Cada sistema tiene un botón **🏠 INICIO** para volver.

No hace falta instalar nada ni tener internet.

## 🧩 Los sistemas

### Equipo 1 – Recetario Visual
- Recetas: **Prepizzas**, **Budín de Naranja** y **Tortafritas**.
- Lista de ingredientes con pictograma, nombre en mayúscula y cantidad.
- Paso a paso: una sola acción por pantalla (4 pasos por receta).
- Botones gigantes **SIGUIENTE PASO** y **VOLVER**.

### Equipo 2 – Herramientas y Seguridad
- Catálogo con 4 herramientas: **Balanza, Batidora/Licuadora, Horno y Matafuegos**.
- Al elegir una, muestra nombre, para qué sirve y una **alerta de seguridad** con fondo rojo.
- Botón **VOLVER** al inicio y al final de cada pantalla.

### Equipo 3 – Comandera (rol: Mozo)
- Productos: **Prepizzas, Budines y Tortas Fritas**.
- Botones **+** y **−** para elegir la cantidad (de 0 a 6).
- Resumen visual del pedido (ej: 🍕 x 6) y botón **ENVIAR A COCINA**.

## 🔧 Cómo funciona sin JavaScript

**Equipos 1 y 2: pantallas con `:target`**
- Cada pantalla es una `<section>` con un `id`.
- Los botones son enlaces: `<a href="#id">`.
- El CSS muestra la pantalla elegida con `:target`.
- Todas las pantallas están apiladas con `z-index`; la que recibe el enlace queda arriba.

**Equipo 3: contador con `:checked`**
- Cada producto tiene 7 botones de opción escondidos (`<input type="radio">`), uno por cantidad.
- Los botones **+** y **−** son `<label>` que activan la opción siguiente o anterior.
- El CSS muestra solo el número de la opción elegida con `:checked`.
- Los `<input>` deben ir **antes** del `<main>`. Si se mueven, el contador deja de funcionar.

## ✂️ Cómo preparar la actividad para los alumnos

Cada archivo tiene comentarios al principio con ideas de bloques para quitar. Algunos ejemplos:

| Sistema | Bloques que se pueden quitar |
|---|---|
| Recetario | Estilo `.boton`, estilo `.ingredientes`, una pantalla de paso |
| Herramientas | Estilo `.tarjeta`, estilo `.alerta`, una pantalla de herramienta |
| Comandera | Estilo `.btn` (+ y −), reglas `:checked`, un selector de producto, el resumen |

Sugerencia: reemplazar el bloque por un comentario como:

```html
<!-- COMPLETAR AQUÍ: pantalla del paso 2 (copiar la del paso 1 y cambiar el texto) -->
```

## 🖼️ Cambiar los emojis por imágenes

Los pictogramas son emojis. Para usar imágenes propias:

```html
<!-- antes -->
<span class="pictograma">🌾</span>

<!-- después -->
<img src="imagenes/harina.png" alt="harina" width="80">
```

## ⚠️ Límites conocidos

- La cantidad máxima de la comandera es **6**. Para más, hay que agregar más radios y estados por producto.
- Los datos no se guardan: al recargar la página, el pedido vuelve a 0.
- El botón **ENVIAR A COCINA** solo muestra una pantalla de confirmación; no envía nada realmente (eso necesitaría JavaScript o un servidor).
- Las cantidades de las recetas son aproximadas.
