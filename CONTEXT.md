# CONTEXT.md - Thermair Corporate Website

> **Última actualización:** 14 de Octubre de 2026  
> **Estado:** Desplegado en producción en Vercel, sincronizado con GitHub. Ajustes mobile aplicados (video 105%, layout 4 filas, sin término guardia).

---

## 🌐 Enlaces Oficiales y Repositorios

- **Sitio Web en Producción (Vercel):** [https://sitioweb-orcin.vercel.app](https://sitioweb-orcin.vercel.app)
- **Repositorio de GitHub:** [https://github.com/5arboles/sitio_web](https://github.com/5arboles/sitio_web)
- **Servidor de desarrollo local:** `http://localhost:8082` (ejecutando `web-v2/` / `sitio_web/`)

---

## 🏗️ Arquitectura y Estructura del Proyecto

El proyecto está organizado en carpetas modulares según las reglas globales:

```text
codigo thermair/
├── CONTEXT.md                  # Este documento (mapa mental y estado actual)
├── README.md                   # Documentación rápida del repositorio
├── sitio_web/                  # Repositorio Git principal conectado a Vercel
│   ├── index.html              # Landing interactiva con Scrollytelling 3D
│   ├── alianzas.html           # Landing Profesionales (Arquitectura, Constructoras, BIM/CAD)
│   ├── climatizacion.html      # Landing Climatización & VRF Inverter con estimador
│   ├── electricidad.html       # Landing Electricidad Corporativa & Media Tensión
│   ├── mantenimiento.html      # Landing Mantenimiento Predictivo & Guardia 24/7
│   ├── vercel.json             # Configuración de Vercel (cleanUrls: true)
│   ├── assets/                 # Video scrub york-scrub.mp4, logos y posters
│   ├── css/                    # style.css y scrollcraft.css
│   └── js/                     # scrollcraft.js
├── web-v2/                     # Carpeta de desarrollo sincronizada con sitio_web
└── scripts/                    # Scripts de utilidades y servidores locales
```

---

## 🎯 Componentes y Decisiones Técnicas Clave

### 1. 3D Scrollytelling Hero (`index.html`)
- **Video Scrubbing:** `assets/york-scrub.mp4` (2.45 MB, 60fps) recortado y optimizado fotograma a fotograma vinculado al scroll del usuario.
- **Dimensiones:** Ocupa el 100% en pantallas móviles/tablets y se ajusta al **90%** en monitores anchos ($\ge 1280\text{px}$) mediante `@media (min-width: 1280px)`.
- **Diseño HUD 4 Cuadrantes:**
  - **Superior Izquierda:** Título (`york-title`) y caja descriptiva translúcida (`york-desc-box`, `backdrop-filter: blur(14px)`).
  - **Superior Derecha:** Badge técnico (`york-badge`), con margen superior (`margin-top: 0.5rem`) y contenedor con `padding-top: 8.75rem` / `8.5rem` para despejar completamente el navbar fijo (~110px).
  - **Inferior Izquierda:** Chips técnicos (COPITEC, Eficiencia A++) e indicador de fase (pills interactivos 01/04 a 04/04).
  - **Inferior Derecha:** Badge acústico (19 dB(A)) y scroll cue ("Deslizá para explorar").
- **Animación de Salida:** Los textos emergen con el scroll y realizan una salida animada hacia **arriba** (`translateY: -38px` con desvanecimiento) simulando que acompañan el flujo natural del scroll.

### 2. Navegación Unificada (5 HTMLs)
- **Enlaces de cabecera:**
  - `[Profesionales](alianzas.html)`
  - `[Electricidad](electricidad.html)`
  - `[Climatización](climatizacion.html)`
  - `[Mantenimiento](mantenimiento.html)`
  - CTA `#contacto-tecnico` ("Asesoramiento Técnico")
- **Identidad:** Solo logo corporativo oficial `assets/thermair-logo.png` (sin textos duplicados al lado).
- **Menú Móvil:** Drawer responsive toggleable en todas las páginas.

### 3. Footer Institucional Unificado
- Fondo oscuro institucional (`bg-primary text-white/80 py-12`).
- Logo oficial en blanco invertido.
- Datos de contacto, sedes (Pilar y CABA) y guardia 24/7.
- Sellos y normativas: **IRAM 2444**, **AEA 90364**, **COPITEC Matriculado**.

---

## 🚀 Comandos Rápidos para Reanudar Mañana

### Levantar Servidor Local
```bash
python3 -m http.server 8082 --directory sitio_web
# Abrir en navegador: http://localhost:8082
```

### Desplegar Cambios a Vercel y GitHub
```bash
cd sitio_web
git add .
git commit -m "Mensaje del cambio"
git push origin main
npx vercel --prod --yes
```
