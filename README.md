```markdown
# 🥤 Smoothie Central | Interfaz de Pedidos con Explorador Nutricional

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

---

## 🌟 Descripción del Proyecto

**Smoothie Central** es una interfaz de usuario interactiva y moderna, diseñada como una aplicación de página única (SPA-like), que simula la experiencia de compra en una tienda de batidos futurista.

El proyecto destaca por su estética **Cyber-Tech Dark Mode** (colores neón primarios y un fondo oscuro) y su funcionalidad **bilingüe (Español/Inglés)** con soporte para contenido estático y dinámico. La aplicación no solo permite a los usuarios seleccionar y personalizar productos, sino que también ofrece un **Explorador Nutricional Interactivo** para consultar el perfil de impacto en la salud de cada ingrediente.

### Características Principales

* **Soporte Multilingüe (ES/EN):** Traducción dinámica de toda la UI, incluyendo nombres de productos, textos de la cesta, *labels* de formularios y descripciones.
* **Explorador Nutricional:** Un panel interactivo que muestra métricas de impacto (Energía, Inmunidad, Recuperación, Digestión) de cada ingrediente al hacer clic.
* **Modal de Personalización Avanzada:** Permite añadir *Boosters* (con cargo extra) y remover ingredientes de los batidos pre-construidos, o crear recetas desde cero (**BYO** - Build Your Own).
* **Cesta Flotante (Floating Cart):** Widget persistente que muestra el recuento de artículos y el total de la compra en tiempo real.
* **Diseño Responsivo:** Uso de Tailwind CSS para una visualización óptima en dispositivos móviles y de escritorio.

---

## 🐛 Correcciones Implementadas (Mejoras de Traducción)

La versión inicial del código presentaba fallos críticos en la gestión de la traducción dinámica, especialmente en elementos que se actualizan fuera del *render* inicial de la página. Las siguientes correcciones se implementaron para garantizar una experiencia bilingüe completa:

1.  **Fallo en la Traducción del Panel de Datos:**
    * **Problema:** Al cambiar el idioma, el nombre del ingrediente seleccionado y las métricas (`Energía`, `Digestión`, etc.) en el panel del explorador permanecían en el idioma anterior.
    * **Solución:** Se modificó la función `updateUI()` para verificar si había un ingrediente seleccionado y, en caso afirmativo, forzar el re-renderizado del `DataPanel` con la traducción actualizada.

2.  **Fallo en la Traducción del Modal de Personalización:**
    * **Problema:** Los nombres de los *Boosters* dentro del modal no se actualizaban al cambiar el idioma si el modal ya había sido abierto previamente.
    * **Solución:** Se añadió una lógica a `updateUI()` para **cerrar y reabrir el modal de personalización** si estaba activo, forzando la re-ejecución de `openCustomizationModal()` y, por lo tanto, la re-renderización de todos los chips de opciones (frutas, *boosters*, y remociones) con el idioma correcto.

---

## 🛠️ Tecnologías Utilizadas

Este proyecto fue construido utilizando herramientas estándar y modernas de desarrollo web para un enfoque *front-end* puro.

| Tecnología | Propósito |
| :--- | :--- |
| **HTML5** | Estructura base de la aplicación. |
| **Vanilla JavaScript** | Toda la lógica de la aplicación (gestión de estado, manipulación del DOM, lógica del carrito, traducciones). |
| **Tailwind CSS** | Framework de CSS utility-first para el estilizado rápido y diseño responsivo. |
| **CSS Personalizado** | Implementación del tema **Cyber-Tech Dark Mode** (colores neón, efectos `glow` y *glassmorphism*). |
| **Font Awesome** | Librería de iconos para mejorar la interfaz de usuario. |

---

## 🚀 Instalación y Uso

Dado que el proyecto está contenido completamente en un único archivo HTML (`fritas.html`), su uso es extremadamente sencillo.

1.  **Descargar el archivo:** Obtenga el archivo HTML.
2.  **Abrir el archivo:** Simplemente haga doble clic en el archivo HTML para abrirlo en su navegador.
3.  **Explorador Nutricional:** Utilice la sección superior para hacer clic en los ingredientes y ver sus perfiles simulados.
4.  **Compra:** Haga clic en el botón de "Añadir y Personalizar" en cualquier smoothie para modificar su receta antes de agregarlo a la cesta.
5.  **Cambio de Idioma:** Utilice el botón **`[EN/ES]`** en la esquina superior derecha para alternar entre idiomas.

---

## ⚙️ Estructura del Código (JavaScript)

El código JavaScript sigue una estructura modular dentro del `<script>` del HTML para mantener el orden y la claridad:

1.  **Gestión de Idioma (`T()`):** Funciones y objeto de `translations` para la internacionalización.
2.  **Base de Datos:** Definición de la estructura de datos (`PRODUCTS`, `BOOSTERS`, etc.) con soporte bilingüe.
3.  **Lógica del Explorador:** Funciones para la gestión de ingredientes únicos, renderizado de la lista y del panel de datos.
4.  **Lógica de Carrito:** Funciones de utilidad para actualizar la vista del carrito y formatear los nombres de los artículos.
5.  **Gestión de Modales:** Funciones para abrir/cerrar modales y manejar la selección de opciones (chips).
6.  **Actualización de la UI (`updateUI()`):** Función central que se ejecuta en la carga y en cada cambio de idioma para re-renderizar todas las partes dinámicas.
7.  **Inicialización:** Detección de `DOMContentLoaded` para la configuración inicial.
```
