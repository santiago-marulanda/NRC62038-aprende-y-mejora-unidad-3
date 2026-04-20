# Sistema de Diseño: Ingeniería de Precisión para "7 Torques"

Este documento establece las directrices visuales y técnicas para la experiencia digital de "7 Torques". El objetivo es trascender el diseño de interfaz genérico, capturando la esencia de un taller de motocicletas de alta gama en Colombia: precisión mecánica, robustez técnica y una sofisticación industrial que proyecte confianza absoluta.

---

## 1. El "Creative North Star": El Manifiesto Mecánico

Nuestra dirección creativa se define como **"Industrialismo de Precisión"**. No estamos construyendo un sitio web; estamos ensamblando una máquina de alto rendimiento. 

A diferencia del diseño "startup" tradicional que abusa de bordes redondeados excesivos y espacios blancos vacíos, este sistema utiliza la **asimetría intencional**, capas tonales profundas y una tipografía autoritaria para evocar la sensación de un manual técnico de lujo o el tablero de una superbike de competición. El diseño debe sentirse "pesado" pero ágil, equilibrando la oscuridad del grafito con destellos de energía cinética.

---

## 2. Paleta de Colores y Arquitectura Cromática

La paleta se aleja de los negros puros (#000) para abrazar carbonos y grises profundos, permitiendo que el color de acento "Racing Orange" respire con máxima intensidad.

### Jerarquía de Superficies y la Regla de "No-Línea"
Queda estrictamente prohibido el uso de bordes sólidos de 1px para separar secciones. La estructura se define mediante el **desplazamiento tonal**.

- **Fondo Base (`background`):** `#111316`. El chasis del diseño.
- **Nidificación de Superficies:** 
    - Utilice `surface_container_low` (`#1a1c1f`) para secciones secundarias sobre el fondo base.
    - Utilice `surface_container_high` (`#282a2d`) para elementos que requieren atención inmediata, como tarjetas de servicio.
- **El Acento Kinético:** El color `primary` (`#ffb693`) y su contenedor `primary_container` (`#ff6b00`) deben usarse con moderación quirúrgica. Solo para llamadas a la acción (CTAs) y puntos críticos de datos técnicos.

### Texturas de Firma: Vidrio y Gradientes
Para evitar una apariencia plana, implemente **Glassmorphism Industrial**:
- Elementos flotantes (menús, notificaciones) deben usar `surface_variant` con un `backdrop-blur` de 12px y una opacidad del 80%.
- Los botones principales deben usar un gradiente sutil de `primary_container` a `primary` en un ángulo de 135° para simular el brillo del metal anodizado.

---

## 3. Tipografía: Autoridad Técnica

La tipografía es el lenguaje de la ingeniería. Hemos seleccionado una combinación que equilibra la frialdad mecánica con la legibilidad humana.

- **Display & Headlines (Space Grotesk):** Una fuente con rasgos geométricos y técnicos. Se debe usar con un `letter-spacing` ligeramente negativo (-0.02em) para dar una sensación de compactación y fuerza.
- **Body & Titles (Manrope):** Una sans-serif moderna y funcional que garantiza que los diagnósticos técnicos y descripciones de servicios sean legibles incluso en condiciones de baja luz (taller).

| Nivel | Token | Fuente | Tamaño | Peso | Uso |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Display LG** | `display-lg` | Space Grotesk | 3.5rem | Bold | Titulares de Hero, Impacto máximo. |
| **Headline MD** | `headline-md` | Space Grotesk | 1.75rem | Medium | Títulos de sección. |
| **Title LG** | `title-lg` | Manrope | 1.375rem | SemiBold | Títulos de tarjetas y servicios. |
| **Body LG** | `body-lg` | Manrope | 1rem | Regular | Texto descriptivo principal. |
| **Label MD** | `label-md` | Space Grotesk | 0.75rem | Bold | Datos técnicos, etiquetas de estado. |

---

## 4. Elevación y Profundidad: Capas de Taller

En "7 Torques", la profundidad no es decorativa; es funcional.

- **Principio de Capas Tonales:** En lugar de sombras externas, utilice el contraste entre `surface_container_lowest` y `surface_container_highest` para crear "hundimientos" o "relieves" en la interfaz.
- **Sombras Ambientales:** Si un elemento debe flotar (como un modal de reserva), la sombra debe ser extra-difusa: `box-shadow: 0 20px 40px rgba(0,0,0,0.4)`. El color de la sombra debe ser una versión oscurecida de la superficie, nunca gris puro.
- **El "Borde Fantasma" (Ghost Border):** Si la accesibilidad requiere un límite, use el token `outline_variant` con una opacidad del 15%. Debe ser casi imperceptible, como una línea de mecanizado en acero.

---

## 5. Componentes Clave

### Botones (Accionadores de Torque)
- **Primary:** Fondo `primary_container`, texto `on_primary_container`. Esquinas redondeadas de `0.5rem` (MD). Sin borde. Al hacer hover, aumentar la saturación del color.
- **Secondary:** Fondo transparente, borde de 1.5px usando `primary` a 40% de opacidad.
- **Tertiary:** Solo texto en `primary`, tipografía `label-md` en mayúsculas para un look de "etiqueta técnica".

### Tarjetas de Servicio (Service Cards)
- Prohibido el uso de líneas divisorias. Use un cambio de color de fondo entre el encabezado de la tarjeta (`surface_container_high`) y el cuerpo (`surface_container`).
- Radio de esquina: `0.75rem` (LG) para un balance entre agresividad y modernidad.

### Inputs de Diagnóstico
- Fondo: `surface_container_low`.
- Borde inferior de 2px en `outline_variant` que se transforma en `primary` cuando el campo está activo. Esto imita la precisión de las herramientas de medición.

### Componente Sugerido: "The Torque Gauge"
Un indicador visual de estado para reparaciones en curso, utilizando un gradiente cónico que va desde `surface_variant` hasta `primary`, simulando un indicador de presión o torque analógico.

---

## 6. Do's & Don'ts (Qué hacer y qué no)

### ✅ Do's
- **Usar espacios amplios:** El "aire" entre componentes debe sentirse intencional, como un taller organizado.
- **Alineación asimétrica:** Experimente con titulares desplazados a la izquierda y bloques de texto a la derecha para romper la monotonía del grid.
- **High Contrast:** Asegure que los CTAs en naranja tengan suficiente contraste sobre los fondos oscuros para cumplir con WCAG AA.

### ❌ Don'ts
- **No usar bordes negros o blancos puros:** Rompen la estética de "metal y aceite" que buscamos.
- **No usar iconos genéricos:** Busque iconografía de trazo grueso y técnico (estilo CAD/Ingeniería).
- **No abusar del naranja:** Si todo resalta, nada resalta. El naranja es para la acción, no para la decoración extensiva.
- **No usar divisores horizontales (`<hr>`):** Use espacios en blanco (`spacing-xl`) o cambios de tono en el fondo para separar el contenido.

---

**Nota Final para Diseñadores:**
Recuerden que "7 Torques" representa la élite del motociclismo en Colombia. Cada píxel debe sentirse como si hubiera sido ajustado con una llave dinamométrica: con precisión, fuerza y propósito.