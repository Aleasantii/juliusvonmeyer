# 🔧 Documentación Técnica

Guía completa para entender y modificar el código del Simulador de Julius Robert Mayer.

---

## 📋 Tabla de Contenidos

1. [Estructura del Código](#estructura-del-código)
2. [HTML](#html)
3. [CSS](#css)
4. [JavaScript](#javascript)
5. [Canvas API](#canvas-api)
6. [Cómo Agregar Características](#cómo-agregar-características)

---

## 📁 Estructura del Código

```
index.html
├── <head>
│   ├── Meta tags (charset, viewport)
│   ├── <style> (CSS incrustado)
│   └── </style>
│
├── <body>
│   ├── <div class="container">
│   │   ├── <header> (Título principal)
│   │   ├── <nav> (Navegación)
│   │   └── <div class="content">
│   │       ├── <section id="biografía">
│   │       ├── <section id="teorias">
│   │       ├── <section id="simulador">
│   │       └── <section id="test">
│   │   └── <footer>
│   │
│   └── <script> (JavaScript incrustado)
└── </body>
```

---

## 🏗️ HTML

### Estructura Semántica

```html
<header>           <!-- Encabezado de la página -->
<nav>              <!-- Navegación entre secciones -->
<section>          <!-- Contenido principal (4 secciones) -->
<canvas>           <!-- Para gráficos interactivos -->
<footer>           <!-- Pie de página -->
```

### Elementos Personalizados

#### 1. Sección de Biografía
```html
<div class="bio-card">
    <div class="bio-image">
        <img src="..." alt="Imagen">
    </div>
    <div class="bio-text">
        <p>Contenido</p>
    </div>
</div>
```

#### 2. Línea Temporal
```html
<div class="timeline">
    <div class="timeline-item">
        <strong>Año</strong> - Evento
    </div>
</div>
```

#### 3. Simuladores
```html
<div class="simulator">
    <div class="simulator-control">
        <label>Control</label>
        <input type="range">
    </div>
    <div class="result-box">
        Resultados
    </div>
    <canvas id="canvas-id"></canvas>
</div>
```

#### 4. Quiz
```html
<div class="quiz-container">
    <div class="question">
        <h4>Pregunta</h4>
        <div class="option">
            <input type="radio" name="qX">
            <label>Opción</label>
        </div>
    </div>
</div>
```

---

## 🎨 CSS

### Variables de Color

```css
/* Colores principales */
#667eea    /* Primario (morado claro) */
#764ba2    /* Secundario (morado oscuro) */
#f8f9fa    /* Fondo claro */
#333       /* Texto oscuro */
#999       /* Texto gris */
#ff6b6b    /* Rojo (calor) */
#4ecdc4    /* Cyan (frío) */
```

### Paleta Completa

| Color | Uso | Hex |
|-------|-----|-----|
| Primario | Botones, títulos | #667eea |
| Secundario | Gradientes | #764ba2 |
| Fondo claro | Fondo general | #f8f9fa |
| Texto | Párrafos | #333 |
| Gris | Subtítulos | #666 |
| Rojo | Calor, error | #ff6b6b |
| Verde | Éxito | #28a745 |
| Cyan | Frío | #4ecdc4 |

### Clases Principales

```css
.container          /* Contenedor principal */
header              /* Encabezado */
nav                 /* Barra de navegación */
.content            /* Contenido principal */
section             /* Secciones individuales */
.simulator          /* Contenedor de simulador */
.quiz-container     /* Contenedor de quiz */
.result-box         /* Caja de resultados */
.btn                /* Botones */
```

### Media Queries

```css
@media (max-width: 768px) {
    /* Estilos para tablet/móvil */
    .bio-card {
        grid-template-columns: 1fr;
    }
}
```

### Animaciones

```css
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Uso */
section.active {
    animation: fadeIn 0.5s;
}
```

---

## ⚙️ JavaScript

### Estructura General

```javascript
// 1. Funciones de Navegación
function showSection(sectionId) { }

// 2. Event Listeners
input.addEventListener('input', function() { })

// 3. Funciones de Simuladores
function updateSimulator() { }
function drawChart() { }

// 4. Funciones del Quiz
function checkQuiz() { }
function resetQuiz() { }

// 5. Inicialización
window.addEventListener('load', function() { })
```

### Funciones Clave

#### 1. Navegación entre Secciones

```javascript
function showSection(sectionId) {
    // Oculta todas las secciones
    const sections = document.querySelectorAll('section');
    sections.forEach(section => section.classList.remove('active'));

    // Muestra la sección seleccionada
    document.getElementById(sectionId).classList.add('active');

    // Actualiza el botón activo
    const navBtns = document.querySelectorAll('.nav-btn');
    navBtns.forEach(btn => btn.classList.remove('active'));
    event.target.classList.add('active');
}
```

#### 2. Event Listeners (Simulador 1)

```javascript
const workInput = document.getElementById('work-input');
workInput.addEventListener('input', function() {
    const work = parseFloat(this.value);
    const heat = work / 4.186;
    
    // Actualiza el DOM
    document.getElementById('display-heat').textContent = heat.toFixed(2);
    
    // Redibuja el gráfico
    drawEquivalenceChart();
});
```

#### 3. Dibujar en Canvas

```javascript
function drawEquivalenceChart() {
    const canvas = document.getElementById('canvas-equivalence');
    const ctx = canvas.getContext('2d');
    
    // Limpiar canvas
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    
    // Dibujar elementos
    ctx.fillStyle = '#667eea';
    ctx.fillRect(x, y, width, height);
    
    // Dibujar texto
    ctx.font = '14px Arial';
    ctx.fillText('Texto', x, y);
}
```

#### 4. Validar Quiz

```javascript
function checkQuiz() {
    const answers = {
        q1: 'b',
        q2: 'b',
        // ...
    };
    
    let score = 0;
    
    // Verificar cada pregunta
    for (let q in answers) {
        const selected = document.querySelector(`input[name="${q}"]:checked`);
        if (selected && selected.value === answers[q]) {
            score++;
        }
    }
    
    // Mostrar resultado
    const percentage = (score / totalQuestions) * 100;
    // ...
}
```

---

## 🎨 Canvas API

### Métodos Principales

```javascript
// Obtener contexto
const ctx = canvas.getContext('2d');

// Limpiar canvas
ctx.clearRect(0, 0, width, height);

// Dibujar rectángulo
ctx.fillStyle = '#667eea';
ctx.fillRect(x, y, width, height);

// Dibujar círculo
ctx.fillStyle = '#ff6b6b';
ctx.beginPath();
ctx.arc(x, y, radius, 0, Math.PI * 2);
ctx.fill();

// Dibujar línea
ctx.strokeStyle = '#333';
ctx.lineWidth = 2;
ctx.beginPath();
ctx.moveTo(x1, y1);
ctx.lineTo(x2, y2);
ctx.stroke();

// Dibujar texto
ctx.font = 'bold 16px Arial';
ctx.textAlign = 'center';
ctx.fillText('Texto', x, y);

// Gradiente
const gradient = ctx.createLinearGradient(x1, y1, x2, y2);
gradient.addColorStop(0, '#667eea');
gradient.addColorStop(1, '#764ba2');
ctx.fillStyle = gradient;
```

### Ejemplo Completo: Dibujar Gráfico de Barras

```javascript
function drawBarChart() {
    const canvas = document.getElementById('my-canvas');
    const ctx = canvas.getContext('2d');
    
    // Limpiar
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    
    // Datos
    const data = [100, 200, 150, 300];
    const barWidth = canvas.width / data.length;
    
    // Dibujar barras
    data.forEach((value, index) => {
        const x = index * barWidth;
        const y = canvas.height - (value / 3);
        
        ctx.fillStyle = '#667eea';
        ctx.fillRect(x + 10, y, barWidth - 20, value / 3);
        
        // Etiqueta
        ctx.fillStyle = '#333';
        ctx.font = '12px Arial';
        ctx.textAlign = 'center';
        ctx.fillText(value, x + barWidth / 2, canvas.height - 5);
    });
}
```

---

## 🚀 Cómo Agregar Características

### 1. Agregar una Nueva Sección

#### Paso 1: HTML
```html
<section id="nueva-seccion">
    <h2>Mi Nueva Sección</h2>
    <p>Contenido aquí</p>
</section>
```

#### Paso 2: Botón de Navegación
```html
<nav>
    <!-- ... botones existentes ... -->
    <button onclick="showSection('nueva-seccion')" class="nav-btn">
        Nueva Sección
    </button>
</nav>
```

#### Paso 3: Estilos (CSS)
```css
#nueva-seccion {
    /* tus estilos */
}
```

### 2. Agregar un Nuevo Simulador

#### Paso 1: HTML
```html
<div class="simulator">
    <h3>Mi Simulador</h3>
    <div class="simulator-control">
        <label for="new-input">Valor: <span id="new-value">100</span></label>
        <input type="range" id="new-input" min="0" max="1000" value="100">
    </div>
    <div class="result-box">
        <p>Resultado: <span id="new-result">0</span></p>
    </div>
    <canvas id="canvas-new"></canvas>
</div>
```

#### Paso 2: JavaScript
```javascript
const newInput = document.getElementById('new-input');
newInput.addEventListener('input', function() {
    const value = parseFloat(this.value);
    const result = value * 2; // Tu cálculo
    
    document.getElementById('new-value').textContent = value;
    document.getElementById('new-result').textContent = result;
    drawNewChart();
});

function drawNewChart() {
    const canvas = document.getElementById('canvas-new');
    const ctx = canvas.getContext('2d');
    
    // Tu código de dibujo aquí
}
```

### 3. Agregar una Pregunta al Quiz

```html
<div class="question">
    <h4>7. ¿Tu nueva pregunta?</h4>
    <div class="option">
        <input type="radio" name="q7" value="a">
        <label>Opción A</label>
    </div>
    <div class="option">
        <input type="radio" name="q7" value="b">
        <label>Opción B</label>
    </div>
</div>
```

```javascript
// En checkQuiz()
const answers = {
    // ... respuestas existentes ...
    q7: 'b'  // Agregar respuesta correcta
};
```

### 4. Personalizar Colores

Busca esta línea en CSS:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

Reemplaza con tus colores:
```css
background: linear-gradient(135deg, #TU_COLOR_1 0%, #TU_COLOR_2 100%);
```

### 5. Agregar Google Analytics

Antes de `</head>`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXX');
</script>
```

---

## 🐛 Debugging

### Abrir Consola (F12)

1. Presiona **F12** o **Ctrl+Shift+I**
2. Ve a la pestaña **Console**
3. Los errores aparecerán en rojo

### Métodos Útiles

```javascript
// Imprimir en consola
console.log('Valor:', variable);

// Error
console.error('Hay un error');

// Advertencia
console.warn('Cuidado');

// Tabla
console.table(objeto);
```

### Ejemplo de Debugging

```javascript
function myFunction() {
    const value = document.getElementById('my-input').value;
    console.log('Valor leído:', value);  // Ver qué se lee
    
    if (!value) {
        console.error('El valor está vacío');
        return;
    }
    
    const result = value * 2;
    console.log('Resultado calculado:', result);  // Ver cálculo
}
```

---

## ⚡ Optimizaciones

### 1. Lazy Loading de Imágenes

```html
<img src="imagen.jpg" loading="lazy" alt="Descripción">
```

### 2. Caché Local

```javascript
// Guardar en localStorage
localStorage.setItem('key', 'value');

// Recuperar
const value = localStorage.getItem('key');
```

### 3. Minificar CSS/HTML

```bash
npm install -g html-minifier
html-minifier --collapse-whitespace index.html > index.min.html
```

---

## 📚 Referencia Rápida de Métodos DOM

```javascript
// Seleccionar elementos
document.getElementById('id')
document.querySelector('selector')
document.querySelectorAll('selector')

// Modificar contenido
element.textContent = 'Texto'
element.innerHTML = '<p>HTML</p>'

// Modificar atributos
element.setAttribute('attr', 'value')
element.getAttribute('attr')
element.classList.add('clase')
element.classList.remove('clase')
element.classList.toggle('clase')

// Event listeners
element.addEventListener('click', function() {})
element.addEventListener('input', function() {})
element.addEventListener('change', function() {})

// Crear elementos
const el = document.createElement('div')
parent.appendChild(el)
parent.removeChild(el)
```

---

## 🔐 Seguridad

### XSS Prevention

Usa `textContent` en lugar de `innerHTML`:

```javascript
// ✅ Seguro
element.textContent = userInput;

// ❌ Peligroso
element.innerHTML = userInput;
```

### Validar Input

```javascript
function isValidNumber(value) {
    return !isNaN(value) && value !== '';
}
```

---

## 📊 Métricas de Rendimiento

```javascript
// Medir tiempo de ejecución
console.time('miTimer');
// ... código ...
console.timeEnd('miTimer');

// Resultados
// miTimer: 1.234ms
```

---

## 🎓 Recursos Adicionales

- [MDN Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [MDN Web Docs](https://developer.mozilla.org/)
- [JavaScript Vanilla Tips](https://javascript.info/)

---

**Versión**: 1.0.0
**Última actualización**: Oct 2024
