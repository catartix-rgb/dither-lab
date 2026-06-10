# DITHER LAB

Web app de **dithering / halftone espectral** en HTML + Canvas, sin dependencias. Convierte un campo de ruido animado (o una imagen) en patrones de puntos iridiscentes con efecto **metal líquido**, render en tiempo real y todo controlable desde una sidebar oscura.

> Un único archivo: [`index.html`](index.html). Ábrelo en el navegador, sin build ni instalación.

## Funciones

- **3 modos de render**: `halftone` · `dither` (Bayer) · `heatmap` (metal líquido suave)
- **Source**
  - **Noise field** — campo de ruido fractal con *domain warping* animado → el look metálico líquido
  - **Imagen** — carga la tuya (drag & drop) o usa el generador de fondos procedural
- **Noise field**: scale · warp (domain) · detail (octavas) · metallic veins
- **Color**: origen (imagen / colormap / mono) · colormaps (Rainbow/spectral, Iridiscente, Magma, Viridis, Océano, Mono) · base palette · fondo · invertir valores
- **Dots**: tamaño según (valor / brillo / uniforme) · dot scale · invertir tamaño
- **Tone**: brightness · contrast · gamma
- **Motion**: animate · speed · **flow** (deforma la imagen con el campo animado)
- **Mask**: center fade (abre un hueco) · dissolve (dispersa los puntos)
- **Grid**: cell size, con lectura `cols × rows · N cells`
- **Export (loop perfecto)**: duración · fps · resolución (supersampling 1×/2×/3×) y 4 formatos:
  - **WebM (VP9)** y **MP4 (H.264)** — vídeo grabado del canvas, ideal para fondos web / visuales
  - **PNG sequence (ZIP)** — fotogramas **sin pérdida**, máxima calidad para tu editor (After Effects/Premiere)
  - **GIF** — preview rápido (256 colores)

  La animación es periódica, así que el clip hace **loop sin costura** (el último fotograma empalma con el primero). Todo se genera en el navegador; nada se sube a ningún servidor.

## Atajos

| Tecla | Acción |
|-------|--------|
| `Space` | play / pausa |
| `R` | randomize (nuevo campo de ruido / fondo, sin repetir) |
| `E` | export PNG |

Arrastra una imagen sobre el lienzo para usarla como fuente.

## Uso

```bash
# clónalo y abre index.html, o sírvelo localmente:
python -m http.server 8777
# -> http://localhost:8777
```

## Créditos

Inspirado en la app *DITHER LAB* de [@KaibaRH](https://x.com/KaibaRH). Implementación original en Canvas 2D.
