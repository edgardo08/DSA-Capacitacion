# DSA-Capacitacion

Plataforma web de capacitación para **DSA Gestiona**, de la Dirección de Servicios Administrativos de la Universidad de Panamá. Todo el contenido está en español.

## Estructura

| Archivo | Función |
|---|---|
| `index.html` | Portada: bienvenida, tarjetas de los 6 módulos, «Tu Progreso» y «Recursos Adicionales». |
| `modulo1.html` | Módulo 1, el único publicado. Es la **plantilla** de los demás. |
| `Logos.png` | Logos del pie de página (`<img src="Logos.png">`). |

Sin build, sin dependencias locales y sin backend. Cada página es un HTML autónomo que carga Tailwind desde `https://cdn.tailwindcss.com`. Para probar, abre el archivo en el navegador o sirve la carpeta con `python3 -m http.server`.

## Módulos

1. Introducción y Fundamentos (publicado, `modulo1.html`)
2. Navegación e Interfaz
3. Creación de Solicitudes
4. Gestión de Expedientes
5. Roles Específicos UG
6. Herramientas Adicionales

Los módulos 2 al 6 aparecen en la portada como tarjetas grises «Próximamente» y no tienen archivo. Al publicar uno, nómbralo `modulo<N>.html` y convierte su tarjeta en enlace igual que la del módulo 1 (borde azul, insignia verde, `<a href>`).

## Reglas para crear o editar módulos

- **Misma estructura que `modulo1.html`:** cabecera con título y barra de progreso, indicadores circulares de pasos, un `div.step-content` por paso con `data-step="N"`, botones Anterior/Siguiente y pie de página.
- **Navegación por pasos:** el script usa `currentStep`, `totalSteps`, `updateUI()`, `nextStep()` y `prevStep()`. Al cambiar el número de pasos, actualiza `totalSteps`, los indicadores `indicator-N` y el texto «Paso X de N».
- **Estilo:** solo clases de Tailwind. Azul (`blue-600`) como color principal, morado como secundario en degradados, verde para completado, fondo `from-blue-50 to-purple-50`.
- **Tono:** claro y directo, tratando al usuario de «usted» en los textos de ayuda, como en `modulo1.html`.
- **Un módulo termina con** un resumen y una verificación de conocimientos.

## Pendientes conocidos

- `modulo1.html` no tiene enlace de regreso a `index.html`.
- «Tu Progreso» en la portada es estático (`0/6`): no guarda avance. Si se implementa, usar `localStorage` con una clave por módulo.
- El inicio de sesión de `modulo1.html` es una demostración: usa `alert()` y no valida nada. No pedir ni guardar credenciales reales.
- El pie de página dice «© 2024».
- «Manual Completo», «Preguntas Frecuentes» y «Soporte Técnico» en la portada son tarjetas sin enlace.

## Cómo trabajar aquí

- Cambios pequeños y revisables: un módulo o una corrección por commit.
- Escribe los mensajes de commit en español, en imperativo («Añade módulo 2»).
- No añadas frameworks ni pasos de build sin que se pida.
