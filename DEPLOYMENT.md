# Guía de Despliegue

Instrucciones paso a paso para desplegar el Simulador de Julius Robert Mayer en diferentes plataformas.

## 🚀 Opción 1: GitHub Pages (Recomendado)

### Paso 1: Crea un repositorio en GitHub

1. Ve a [GitHub.com](https://github.com/new)
2. Nombre del repositorio: `julius-mayer-simulator`
3. Descripción: "Simulador interactivo sobre Julius Robert Mayer y sus teorías"
4. Selecciona "Public"
5. Haz clic en "Create repository"

### Paso 2: Clona el repositorio

```bash
# Clona tu repositorio vacío
git clone https://github.com/tu-usuario/julius-mayer-simulator.git
cd julius-mayer-simulator
```

### Paso 3: Agrega los archivos

```bash
# Copia todos los archivos de este proyecto al directorio
cp /ruta/local/* .

# Verifica que están todos
ls -la
# Deberías ver: index.html, README.md, package.json, .gitignore, etc.
```

### Paso 4: Haz un commit y push

```bash
git add .
git commit -m "Initial commit: Julius Robert Mayer Simulator v1.0"
git branch -M main
git push -u origin main
```

### Paso 5: Activa GitHub Pages

1. Ve a tu repositorio en GitHub
2. Haz clic en **Settings** (Configuración)
3. En la barra lateral, haz clic en **Pages**
4. En "Source", selecciona **main** branch
5. Haz clic en **Save**
6. GitHub te dirá: "Your site is live at: https://tu-usuario.github.io/julius-mayer-simulator"

### Paso 6: Verifica el despliegue

Espera 1-2 minutos y luego:
- Abre: `https://tu-usuario.github.io/julius-mayer-simulator`
- ¡Listo! Tu sitio está en vivo

---

## 🌐 Opción 2: Netlify (Alternativa fácil)

### Paso 1: Prepara tu repositorio

```bash
git init
git add .
git commit -m "Initial commit"
```

### Paso 2: Sube a GitHub

```bash
git remote add origin https://github.com/tu-usuario/julius-mayer-simulator.git
git push -u origin main
```

### Paso 3: Conecta con Netlify

1. Ve a [Netlify.com](https://netlify.com)
2. Haz clic en "Sign Up" (o "Sign In")
3. Selecciona "GitHub" para conectar tu cuenta
4. Autoriza a Netlify
5. Haz clic en "New site from Git"
6. Selecciona tu repositorio
7. Deja la configuración por defecto
8. Haz clic en "Deploy site"

### Beneficios de Netlify:
✅ Despliegue automático en cada push
✅ Dominio personalizado gratuito
✅ HTTPS automático
✅ Estadísticas de tráfico
✅ Variables de entorno

---

## 💻 Opción 3: Vercel (Para desarrolladores)

### Paso 1: Instala Vercel CLI

```bash
npm install -g vercel
```

### Paso 2: Inicia sesión

```bash
vercel login
```

### Paso 3: Despliega

```bash
vercel
# Sigue las instrucciones interactivas
```

---

## 🖥️ Opción 4: Servidor Local (Desarrollo)

### Usando Python 3

```bash
cd julius-mayer-simulator
python -m http.server 8000
# Abre: http://localhost:8000
```

### Usando Node.js

```bash
npm install -g http-server
http-server
# Abre: http://localhost:8080
```

### Usando PHP

```bash
cd julius-mayer-simulator
php -S localhost:8000
# Abre: http://localhost:8000
```

---

## 📊 Monitoreo de Despliegue

### GitHub Pages

**Monitorea el despliegue:**
1. Ve a tu repositorio
2. Haz clic en **Actions**
3. Verás el estado del despliegue
4. Los errores aparecerán allí

**Estadísticas de tráfico:**
1. Settings → Pages
2. Ver el gráfico de visitantes

### Netlify

**Dashboard:**
1. Inicia sesión en [Netlify](https://app.netlify.com)
2. Selecciona tu sitio
3. Ve al tab "Analytics" para estadísticas
4. Ve al tab "Deploys" para ver el historial

---

## 🔄 Actualizar tu Sitio

Una vez desplegado, puedes actualizar el contenido fácilmente:

### GitHub Pages (automático)

```bash
# Haz cambios en los archivos
nano index.html

# Haz un commit
git add .
git commit -m "Actualizar simulador de Carnot"

# Push
git push origin main

# GitHub Pages se actualiza automáticamente en 1-2 minutos
```

### Netlify (automático)

Simplemente haz push a GitHub. Netlify detectará los cambios y redesplegará automáticamente.

---

## 🎯 Configuración de Dominio Personalizado

### Con GitHub Pages

1. Ve a Settings → Pages
2. En "Custom domain", escribe: `mi-dominio.com`
3. Haz clic en "Save"
4. En tu registrador de dominios (GoDaddy, Namecheap, etc.):
   - Crea un registro CNAME:
     ```
     CNAME: tu-usuario.github.io
     ```

### Con Netlify

1. Settings → Domain management
2. Haz clic en "Add custom domain"
3. Escribe tu dominio
4. Sigue las instrucciones de DNS

---

## ⚡ Optimización para Producción

### 1. Minificar archivos

El proyecto actual es HTML monolítico, pero puedes minificar así:

```bash
# Instala htmlmin
npm install -g html-minifier

# Minifica
html-minifier --collapse-whitespace --remove-comments index.html > index.min.html
```

### 2. Agregar caché

En GitHub Pages (automático): 30 minutos
En Netlify: configurable en Settings

### 3. Medir rendimiento

```bash
# Usa PageSpeed Insights
# https://pagespeed.web.dev/
# Tu URL: https://tu-usuario.github.io/julius-mayer-simulator
```

---

## 🔒 Seguridad

### HTTPS

✅ GitHub Pages: Automático
✅ Netlify: Automático
✅ Vercel: Automático

### Proteger tu repositorio

1. Settings → Branch protection rules
2. Requiere revisión de PR
3. Requiere checks para pasar

---

## 🚨 Solucionar Problemas

### "La página no aparece después de 5 minutos"

**Solución:**
```bash
# Verifica que Git está correctamente configurado
git config --list

# Reintenta el push
git push origin main -f

# Ve a Settings → Pages y verifica la rama seleccionada
```

### "Error 404 después de desplegar"

**Solución:**
- Verifica que el archivo se llama exactamente `index.html`
- Asegúrate de que está en la raíz del repositorio
- Borra la caché del navegador: Ctrl+Shift+Delete

### "Las imágenes no cargan"

**Causa:** Las imágenes son de URLs externas (Wikipedia)
**Solución:**
```bash
# Descarga las imágenes localmente
mkdir assets
# Coloca las imágenes aquí
# Actualiza las URLs en index.html
```

---

## 📈 Estadísticas y Analytics

### Agregar Google Analytics

1. Ve a [Google Analytics](https://analytics.google.com)
2. Crea una nueva propiedad
3. Copia tu ID de seguimiento (G-XXXXXXXXX)
4. Agrega a index.html antes de `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXX');
</script>
```

### Netlify Analytics (Built-in)

1. Settings → Analytics
2. "Enable Netlify Analytics"
3. Suscripción: $9/mes

---

## 🎉 Verificación Final

Después de desplegar, verifica:

- [ ] La página carga sin errores
- [ ] Todos los simuladores funcionan
- [ ] El test responde correctamente
- [ ] La página es responsive en móvil
- [ ] Las imágenes cargan
- [ ] Los gráficos Canvas se renderizan
- [ ] No hay errores en la consola (F12)
- [ ] La URL es correcta

---

## 📚 Documentación Oficial

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Netlify Docs](https://docs.netlify.com/)
- [Vercel Docs](https://vercel.com/docs)

---

**¡Tu proyecto está listo para ser visto por el mundo!** 🌍
