# Thermair - Sitio Web Corporativo

Sitio web corporativo y técnico multi-página para **Thermair | Ingeniería en Climatización y Distribución Eléctrica**.

---

## 🌐 Enlaces en Vivo y Repositorio

- **Sitio Web en Producción (Vercel):** [https://sitioweb-orcin.vercel.app](https://sitioweb-orcin.vercel.app)
- **Repositorio en GitHub:** [https://github.com/5arboles/sitio_web](https://github.com/5arboles/sitio_web)

---

## 📁 Estructura del Proyecto

```text
codigo thermair/
├── sitio_web/                 # Repositorio Git principal desplegado en Vercel
│   ├── index.html             # Landing interactiva con Scrollytelling 3D
│   ├── alianzas.html          # Profesionales: Arquitectos & Constructoras
│   ├── electricidad.html      # Electricidad Corporativa, MT/BT & Subestaciones
│   ├── climatizacion.html     # Climatización, VRF Inverter & Estimador térmico
│   ├── mantenimiento.html     # Mantenimiento Predictivo & Guardia 24/7
│   ├── assets/                # Video scrub york-scrub.mp4, posters y logos
│   ├── css/                   # style.css y scrollcraft.css
│   └── js/                    # scrollcraft.js
├── web-v2/                    # Carpeta de desarrollo local sincronizada
├── CONTEXT.md                 # Mapa mental y documentación detallada
└── README.md                  # Este documento
```

---

## 🚀 Cómo probar localmente

```bash
python3 -m http.server 8082 --directory sitio_web
```
Luego abrí en tu navegador: [http://localhost:8082](http://localhost:8082)

---

## 🛠️ Características Principales Implementadas

1. **Scrollytelling 3D Interactivo (`index.html`):**
   - Video de despiece YORK Inverter que responde dinámicamente al scroll.
   - Escala al 90% en pantallas $\ge 1280\text{px}$.
   - Disposición HUD de 4 cuadrantes con badge a la derecha, título y descripción a la izquierda, y chips en esquinas inferiores.
   - Holgura y despeje superior total respecto a la barra de navegación fija.
2. **Navegación Unificada:**
   - Botones en cabecera: **Profesionales**, **Electricidad**, **Climatización**, **Mantenimiento** y CTA técnico.
   - Menú móvil desplegable responsive sincronizado en todas las páginas.
3. **Footer Institucional Unificado:**
   - Pie de página oscuro minimalista con logo corporativo oficial, normativas (IRAM 2444, AEA 90364, COPITEC) y vías de contacto.
