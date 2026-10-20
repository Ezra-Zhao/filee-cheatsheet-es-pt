# 🍩 Guía rápida: Filee — convierte archivos arrastrando, sin subir nada (ES · PT)

[🇪🇸 Español](#-español) · [🇵🇹 Português](#-português) · [🇬🇧 English summary](#-english-summary)

Una sola página para usar **Filee** (de KnifeLemon): el conversor gratuito y de código abierto que funciona arrastrando. Mantienes pulsada una tecla, arrastras tus archivos, los sueltas sobre el formato en la rosca que aparece junto a tu cursor, y el archivo convertido queda al lado del original. Más de 244 formatos, sin cuentas, sin subir nada a ningún servidor y sin tener Office instalado.

**Autor:** Guangyi Zhao · Octubre 2026

Proyecto original: https://github.com/KnifeLemon/Filee (7.656 estrellas y 463 forks, consultado el 20 de octubre de 2026) · Sitio: filee.sh

> **Nota de autoría:** esta guía es una síntesis original, redactada por el autor a partir de la documentación pública del proyecto y de su propio uso. No es una traducción ni una copia de la documentación oficial, y no es un proyecto oficial de Filee. Para el detalle completo, ve al repositorio enlazado.

---

## 🇪🇸 Español

### El gesto, en cuatro pasos

1. **Instala Filee y déjalo residente.** En Windows, el instalador o la versión portable de la página de Releases de GitHub; en macOS y Linux está en vista previa (abajo, la tabla de plataformas).
2. **Mantén pulsada la tecla y arrastra.** `Ctrl` en Windows y Linux; `Option` en macOS. Puedes arrastrar uno o varios archivos a la vez.
3. **Suelta sobre el formato.** En tu cursor se abre una rosca solo con los formatos que tienen sentido para esos archivos; dejas caer el archivo sobre el que quieres.
4. **Recoge el resultado junto al original.** La conversión es local y el archivo nuevo aparece en la misma carpeta.

Extras que conviene conocer: con `Tab` o la rueda del ratón volteas la rosca para ver formatos menos comunes y herramientas; las rutas de varios pasos se resuelven solas (por ejemplo HWP → HWPX → DOCX); también puedes arrastrar una imagen o un enlace directamente desde Chrome, Edge, Firefox o Safari (queda en tu carpeta de Descargas), usar el menú contextual del explorador, una zona de soltar, o **carpetas vigiladas** que convierten todo lo que cae en ellas.

### La tabla de formatos

Sin marca: funciona recién instalado, sin Office, sin Hancom Office y sin LibreOffice. Con marca: necesita un motor opcional que Filee descarga solo cuando hace falta — ¹ Ghostscript · ² LibreOffice · ³ Pandoc · ⁴ calibre · ⁵ FFmpeg. (Selección de formatos; la lista completa está en el repositorio.)

| Categoría | Desde | Hacia |
|---|---|---|
| **Imágenes** | JPG, PNG, WEBP, AVIF, TIFF, BMP, GIF, HEIC, PSD, RAW de cámara (CR2, NEF, ARW, DNG), DICOM, OpenEXR | Entre sí, PDF, SVG (trazado), redimensionar |
| **Vectoriales** | SVG, SVGZ, EMF, WMF, AI · EPS, PS ¹ · CDR, VSD, ODG ² | PDF vectorial, imágenes, SVG → DXF/DWG |
| **PDF** | PDF | DOCX, TXT, PNG/JPG, PPTX (una imagen por página), SVG ²; unir, dividir, comprimir |
| **Documentos** | DOCX, DOC, ODT, RTF, WPS, Pages ², EML/MSG, OFD (lectura) | PDF, DOCX, EPUB, TXT, HTML |
| **Hojas de cálculo** | XLSX, XLS, ODS, CSV, TSV, Numbers ² | PDF, XLSX, ODS, CSV, JSON, HTML |
| **Presentaciones** | PPTX, PPT, ODP, Keynote ² | PDF, PNG/JPG, DOCX |
| **HWP** | HWP, HWPX | PDF, PNG, DOCX, TXT, Markdown, HTML |
| **Texto y marcado** | TXT, Markdown, HTML, reStructuredText, LaTeX, Org, AsciiDoc, Typst, Jupyter ³ | PDF, DOCX, EPUB, entre sí, PPTX ³ |
| **Libros electrónicos** | EPUB, MOBI, AZW3, FB2, CBZ/CBR · CHM, LIT ⁴ | PDF, EPUB, DOCX, TXT, HTML |
| **Vídeo** ⁵ | MP4, MOV, MKV, WEBM, AVI, WMV, FLV | MP4 (H.264, HEVC, AV1), WEBM, GIF, extraer el audio, subtítulos (SRT, ASS, WebVTT) |
| **Audio** ⁵ | MP3, M4A, WAV, FLAC, OGG, OPUS, WMA, DSD, DTS, AC3 | MP3, M4A, WAV, FLAC, OGG, OPUS |
| **Subtítulos** | SRT, ASS/SSA, WebVTT, SAMI, LRC, TTML | Entre sí, siempre en UTF-8 |
| **Comprimidos** | ZIP, 7Z, RAR, TAR, ISO, DMG, CAB | Extraer; ZIP, 7Z, TAR; varios archivos → un ZIP |
| **CAD** | DWG, DXF | PDF, SVG, PNG, DWG ↔ DXF |
| **Fuentes** | TTF, OTF, WOFF, WOFF2, EOT | Entre sí |
| **Datos** | JSON, YAML, TOML, XML, vCard | Entre sí, CSV, XLSX |
| **Modelos 3D** | GLB, glTF, STL, OBJ, 3MF, PLY, FBX (lectura) | Entre sí, imagen de vista previa |
| **Geodatos** | Shapefile, GeoJSON, KML, KMZ, GPX | Entre sí, CSV/XLSX/JSON (las coordenadas salen en WGS 84) |

Un detalle práctico: codificar a HEIC y todo el vídeo y el audio pasan por FFmpeg ⁵, así que esas conversiones también «llevan marca» aunque la categoría parezca básica.

### Plataformas

| Sistema | Estado | Lo que hay que saber |
|---|---|---|
| Windows 10/11 | Completo | Instalador o portable; el instalador puede añadir el menú del Explorador, el arranque con Windows y el comando `filee` |
| macOS 14+ | Vista previa | La aplicación no está notarizada: el primer arranque se permite en Ajustes del Sistema → Privacidad y seguridad → «Abrir de todos modos» |
| Linux (Ubuntu 22.04+) | Vista previa | El gesto de arrastre necesita X11; en Wayland se usa la zona de soltar o el menú contextual del gestor de archivos |

La interfaz ya está en español; **todavía no en portugués** — de ahí esta guía. Filee avisa de las versiones nuevas en su menú y se actualiza solo, conservando tus ajustes y motores.

### La línea de comandos, en tres líneas

```bash
filee convert foto.heic --to jpg
filee convert *.png --to webp --quality 80 -o convertidos
filee watch ~/Entrada --to pdf --move-originals
```

La primera convierte un archivo; la segunda, un lote entero con calidad fijada; la tercera vigila una carpeta y convierte todo lo que cae en ella. El comando usa los mismos motores y ajustes que la aplicación.

### Privacidad, en una línea

Todo se convierte en tu ordenador: Filee no sube archivos, no recoge datos de uso ni telemetría; solo sale a internet para comprobar si hay una versión nueva (se puede desactivar), para descargar los motores que tú elijas y cuando tú pulsas un enlace.

### ⚠️ Errores típicos

- **Seguir subiendo archivos sensibles a conversores web.** Contratos, nóminas, documentos de identidad: en los conversores en línea el archivo sale de tu máquina (y suele pedir registro y poner límites de tamaño). Con Filee la conversión es local: esa es la diferencia que importa.
- **Asustarse con el aviso de Windows.** El instalador aún no lleva firma de código, así que SmartScreen puede advertir al ejecutarlo: «Más información» → «Ejecutar de todas formas». El proyecto lo documenta; la firma está en trámite.
- **Pedir un formato «con marca» sin su motor.** Si una conversión marcada ¹–⁵ no aparece o falla, falta su motor opcional: Filee lo descarga cuando lo necesitas, no tienes que instalar nada a mano.

---

## 🇵🇹 Português

### O gesto, em quatro passos

1. **Instale o Filee e deixe-o residente.** No Windows, o instalador ou a versão portátil da página de Releases do GitHub; no macOS e no Linux ele está em prévia (abaixo, a tabela de plataformas).
2. **Segure a tecla e arraste.** `Ctrl` no Windows e no Linux; `Option` no macOS. Dá para arrastar um ou vários arquivos de uma vez.
3. **Solte sobre o formato.** No seu cursor abre-se uma rosca só com os formatos que fazem sentido para aqueles arquivos; você solta o arquivo sobre o formato que quer.
4. **Pegue o resultado ao lado do original.** A conversão é local e o arquivo novo aparece na mesma pasta.

Extras que vale conhecer: com `Tab` ou a roda do mouse você vira a rosca para ver formatos menos comuns e ferramentas; rotas de vários passos se resolvem sozinhas (por exemplo HWP → HWPX → DOCX); também dá para arrastar uma imagem ou um link direto do Chrome, Edge, Firefox ou Safari (fica na sua pasta de Downloads), usar o menu de contexto do explorador, uma zona de soltar, ou **pastas vigiadas**, que convertem tudo o que cai nelas.

### A tabela de formatos

Sem marca: funciona recém-instalado, sem Office, sem Hancom Office e sem LibreOffice. Com marca: precisa de um motor opcional que o Filee baixa só quando faz falta — ¹ Ghostscript · ² LibreOffice · ³ Pandoc · ⁴ calibre · ⁵ FFmpeg. (Seleção de formatos; a lista completa está no repositório.)

| Categoria | De | Para |
|---|---|---|
| **Imagens** | JPG, PNG, WEBP, AVIF, TIFF, BMP, GIF, HEIC, PSD, RAW de câmera (CR2, NEF, ARW, DNG), DICOM, OpenEXR | Entre si, PDF, SVG (vetorizado), redimensionar |
| **Vetoriais** | SVG, SVGZ, EMF, WMF, AI · EPS, PS ¹ · CDR, VSD, ODG ² | PDF vetorial, imagens, SVG → DXF/DWG |
| **PDF** | PDF | DOCX, TXT, PNG/JPG, PPTX (uma imagem por página), SVG ²; juntar, dividir, comprimir |
| **Documentos** | DOCX, DOC, ODT, RTF, WPS, Pages ², EML/MSG, OFD (leitura) | PDF, DOCX, EPUB, TXT, HTML |
| **Planilhas** | XLSX, XLS, ODS, CSV, TSV, Numbers ² | PDF, XLSX, ODS, CSV, JSON, HTML |
| **Apresentações** | PPTX, PPT, ODP, Keynote ² | PDF, PNG/JPG, DOCX |
| **HWP** | HWP, HWPX | PDF, PNG, DOCX, TXT, Markdown, HTML |
| **Texto e marcação** | TXT, Markdown, HTML, reStructuredText, LaTeX, Org, AsciiDoc, Typst, Jupyter ³ | PDF, DOCX, EPUB, entre si, PPTX ³ |
| **E-books** | EPUB, MOBI, AZW3, FB2, CBZ/CBR · CHM, LIT ⁴ | PDF, EPUB, DOCX, TXT, HTML |
| **Vídeo** ⁵ | MP4, MOV, MKV, WEBM, AVI, WMV, FLV | MP4 (H.264, HEVC, AV1), WEBM, GIF, extrair o áudio, legendas (SRT, ASS, WebVTT) |
| **Áudio** ⁵ | MP3, M4A, WAV, FLAC, OGG, OPUS, WMA, DSD, DTS, AC3 | MP3, M4A, WAV, FLAC, OGG, OPUS |
| **Legendas** | SRT, ASS/SSA, WebVTT, SAMI, LRC, TTML | Entre si, sempre em UTF-8 |
| **Compactados** | ZIP, 7Z, RAR, TAR, ISO, DMG, CAB | Extrair; ZIP, 7Z, TAR; vários arquivos → um ZIP |
| **CAD** | DWG, DXF | PDF, SVG, PNG, DWG ↔ DXF |
| **Fontes** | TTF, OTF, WOFF, WOFF2, EOT | Entre si |
| **Dados** | JSON, YAML, TOML, XML, vCard | Entre si, CSV, XLSX |
| **Modelos 3D** | GLB, glTF, STL, OBJ, 3MF, PLY, FBX (leitura) | Entre si, imagem de prévia |
| **Geodados** | Shapefile, GeoJSON, KML, KMZ, GPX | Entre si, CSV/XLSX/JSON (as coordenadas saem em WGS 84) |

Um detalhe prático: codificar para HEIC e todo o vídeo e áudio passam pelo FFmpeg ⁵, então essas conversões também «têm marca», mesmo quando a categoria parece básica.

### Plataformas

| Sistema | Estado | O que é preciso saber |
|---|---|---|
| Windows 10/11 | Completo | Instalador ou portátil; o instalador pode adicionar o menu do Explorador, a inicialização com o Windows e o comando `filee` |
| macOS 14+ | Prévia | O app não é notarizado: a primeira abertura se libera em Ajustes do Sistema → Privacidade e Segurança → «Abrir Mesmo Assim» |
| Linux (Ubuntu 22.04+) | Prévia | O gesto de arrastar precisa de X11; no Wayland usa-se a zona de soltar ou o menu de contexto do gerenciador de arquivos |

A interface já está em espanhol; **ainda não em português** — daí este guia. O Filee avisa sobre versões novas no menu e se atualiza sozinho, mantendo suas configurações e motores.

### A linha de comando, em três linhas

```bash
filee convert foto.heic --to jpg
filee convert *.png --to webp --quality 80 -o convertidos
filee watch ~/Entrada --to pdf --move-originals
```

A primeira converte um arquivo; a segunda, um lote inteiro com qualidade definida; a terceira vigia uma pasta e converte tudo o que cai nela. O comando usa os mesmos motores e configurações do aplicativo.

### Privacidade, numa linha

Tudo se converte no seu computador: o Filee não envia arquivos, não coleta dados de uso nem telemetria; só sai para a internet para verificar se há uma versão nova (dá para desativar), para baixar os motores que você escolher e quando você clica num link.

### ⚠️ Erros típicos

- **Continuar enviando arquivos sensíveis a conversores web.** Contratos, contracheques, documentos de identidade: nos conversores online o arquivo sai da sua máquina (e eles costumam pedir cadastro e impor limites de tamanho). Com o Filee a conversão é local: essa é a diferença que importa.
- **Assustar-se com o aviso do Windows.** O instalador ainda não tem assinatura de código, então o SmartScreen pode avisar ao executá-lo: «Mais informações» → «Executar assim mesmo». O projeto documenta isso; a assinatura está em andamento.
- **Pedir um formato «com marca» sem o motor.** Se uma conversão marcada ¹–⁵ não aparece ou falha, falta o motor opcional dela: o Filee baixa quando você precisa, não é preciso instalar nada à mão.

---

## 🇬🇧 English summary

One-page cheat sheet (Spanish + Portuguese) for **Filee** (KnifeLemon): the free, open-source (MIT) file converter you operate by dragging. Hold Ctrl (Option on macOS), drag one or more files, and a donut of only the formats that make sense appears at your cursor; drop on a format and the converted file lands next to the original — fully offline, no account, no upload, no Office required. The sheet maps the 244+ formats across the README's 18 category rows (images, vector, PDF, documents, spreadsheets, presentations, HWP, text/markup, e-books, video, audio, subtitles, archives, CAD, fonts, data, 3D models, geospatial) and marks which conversions work out of the box and which need an optional engine that Filee downloads on demand: Ghostscript (EPS/PS), LibreOffice (legacy formats), Pandoc (markup), calibre (legacy e-books), FFmpeg (video, audio, HEIC encoding). It also covers the Tab/wheel flip side of the donut, browser drag-in, watch folders, platform status (Windows 10/11 complete; macOS 14+ and Linux previews, with the not-notarized first-launch step and the X11-vs-Wayland note), the three-line CLI (`convert`, batch with `--quality`, `watch`), and the privacy line: no uploads, no telemetry, internet only for update checks and engine downloads. The UI already ships in Spanish but not yet in Portuguese — the gap this sheet fills. Typical mistakes: uploading sensitive files to web converters out of habit, panicking at the SmartScreen warning (the installer is not code-signed yet), and requesting an engine-marked format before its engine is fetched. Original synthesis by the author from the project's public documentation; not an official document and not a translation.

**Author:** Guangyi Zhao · October 2026 · MIT License
