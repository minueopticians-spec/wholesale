# Minuë Wholesale Landing Page

## Despliegue rápido en Vercel

### Paso 1: Subir a GitHub
```bash
cd minue-wholesale
git init
git add .
git commit -m "Minuë wholesale landing"
git remote add origin https://github.com/acardia91/minue-wholesale.git
git push -u origin main
```

### Paso 2: Conectar con Vercel
1. Ve a https://vercel.com/dashboard
2. Click "Add New" → "Project"
3. Importa el repo `minue-wholesale`
4. Framework: **Vite** (se detecta automáticamente)
5. Click "Deploy"

### Paso 3: Configurar subdominio
En Vercel (Settings → Domains):
1. Añade: `wholesale.minueopticians.com`
2. Vercel te dará un registro CNAME

En tu DNS (donde tengas minueopticians.com):
1. Añade registro CNAME:
   - Nombre: `wholesale`
   - Valor: `cname.vercel-dns.com`
2. Espera 5-10 minutos a que propague

¡Listo! Tu landing estará en: https://wholesale.minueopticians.com

---

## Cómo cambiar imágenes

### Opción A: Imágenes locales
1. Mete tus fotos en `/public/img/`
   - hero.jpg (foto principal campaña)
   - familia.jpg (sección familia)
   - sevilla.jpg (sección Sevilla)
   - estilo.jpg (sección estilo)
   - packaging.jpg (sección packaging)

2. En `src/App.jsx`, cambia las constantes base64 por rutas:
```javascript
const IMG_HERO = "/img/hero.jpg";
const IMG_FAMILIA = "/img/familia.jpg";
const IMG_SEVILLA = "/img/sevilla.jpg";
const IMG_ESTILO = "/img/estilo.jpg";
const IMG_PACKAGING = "/img/packaging.jpg";
```

### Opción B: URLs de Shopify CDN
En `src/App.jsx`, cambia las constantes por URLs de tu Shopify:
```javascript
const IMG_HERO = "https://www.minueopticians.com/cdn/shop/files/tu-foto-hero.jpg";
```

### Opción C: Cloudinary (recomendado para optimización)
1. Sube fotos a Cloudinary (gratis hasta 25GB)
2. Usa las URLs transformadas:
```javascript
const IMG_HERO = "https://res.cloudinary.com/tu-cuenta/image/upload/w_800,q_auto/hero.jpg";
```

---

## Cómo cambiar textos
Todos los textos están en el objeto `TX` al principio de `src/App.jsx`.
Cada idioma tiene su bloque: ES, FR, DE, EN.

## Cómo cambiar el enlace del catálogo
Busca `drive.google.com/PEGA-TU-ENLACE-AQUI` y reemplaza por tu enlace real de Google Drive.

## Cómo cambiar el logo
Los logos están como base64 en las constantes `LOGO_D` (negro) y `LOGO_W` (blanco).
Para usar archivos:
1. Pon los logos en `/public/img/logo-dark.png` y `/public/img/logo-white.png`
2. Cambia las constantes:
```javascript
const LOGO_D = "/img/logo-dark.png";
const LOGO_W = "/img/logo-white.png";
```
