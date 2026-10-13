# Profertil · Color Browser

Herramienta web estática (HTML + CSS + JS vanilla, sin build step) para consultar la paleta del **Sistema de marca Profertil 2026**: copiar los códigos de cada color y elegir una combinación del manual. Comparte el lenguaje visual del [Icon Browser](https://github.com/bongstudio-dev/profertil-icon-browser) y del [Pattern Generator](https://github.com/bongstudio-dev/profertil-pattern-generator).

Publicada en https://bongstudio-dev.github.io/profertil-color-browser/

## Uso

```bash
cd profertil-color-browser
python3 -m http.server 5055     # o: npm run dev
# abrí http://localhost:5055
```

> No usar el puerto 5060: Chrome lo bloquea (ERR_UNSAFE_PORT).

## Funcionalidad

- **Paleta completa**: los 8 colores con HEX, RGB, CMYK y Pantone. Un clic en cualquier código lo copia; un clic en el color copia el formato elegido arriba ("Copiar en").
- **Combinaciones**: los tres niveles del manual (primaria, secundarias, terciarias) con sus proporciones en torta, animadas. Se puede ver cada una sobre fondo Marfil y copiar la combinación entera.
- **Color y texto**: los 27 usos correctos de texto sobre fondo. Un clic copia los dos códigos.
- **Descargar muestras (.ase)**: archivo Adobe Swatch Exchange con la paleta en CMYK y en RGB, para cargar en Illustrator, InDesign o Photoshop (panel Muestras, "Abrir biblioteca de muestras").
- **Links directos**: `#paleta`, `#combinaciones` y `#texto` abren cada vista.

## De dónde salen los datos

Todo está en `script.js`, al principio, y sale del **Manual de Marca v1.1.4**:

| Constante | Sección del manual |
|---|---|
| `COLORS` | 03.02.03, Paleta completa (p. 45) |
| `LEVELS` | 03.05.01 Jerarquías (p. 46) y 03.06.01 Proporciones (p. 47) |
| `TEXT_PAIRS` | 03.07.01, Color y texto (p. 48) |

Las tortas siguen las del manual: secundarias 70/30 (lo que dice el texto) y terciarias 50/25/25 (lo que dibuja la torta; el texto solo dice "proporciones variables, siempre con un color protagonista"). Sobre color, las etiquetas van en blanco, también sobre Amarillo, como en el manual.

Si cambia un valor en el manual, se corrige en `COLORS` y el resto (tarjetas, combinaciones, archivo .ase) se actualiza solo.

---

Sistema de marca por **[Bong](https://bongstudio.ar)**.
