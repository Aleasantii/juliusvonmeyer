# Guía de Contribución

¡Gracias por tu interés en contribuir al Simulador de Julius Robert Mayer! Esta guía te ayudará a entender cómo colaborar efectivamente.

## 📋 Código de Conducta

Por favor, sé respetuoso y constructivo en todas las interacciones.

## 🤝 Cómo Contribuir

### 1. Reportar Bugs

Si encuentras un bug, abre un issue en GitHub incluyendo:
- **Descripción clara** del problema
- **Pasos para reproducirlo**
- **Comportamiento esperado**
- **Comportamiento actual**
- **Navegador y sistema operativo**

Ejemplo:
```
Título: Los simuladores no cargan en Firefox
Descripción: Cuando abro la página en Firefox, los gráficos de Canvas están en blanco.
Pasos:
1. Abrir index.html en Firefox 120+
2. Navegar a la sección "Simulador"
3. Los gráficos no aparecen
Esperado: Ver gráficos animados
Actual: Canvas vacío
SO: Windows 11, Firefox 120
```

### 2. Sugerir Mejoras

Propuestas de nuevas características:
- Describe el caso de uso
- Explica por qué sería útil
- Sugiere posibles soluciones

Ejemplo:
```
Solicitud: Agregar tema oscuro
Justificación: Muchos usuarios prefieren interfaces oscuras para reducir 
fatiga ocular. Sería una adición valiosa.
Solución sugerida: Usar CSS media queries y variables CSS
```

### 3. Enviar Pull Requests

#### Proceso:

1. **Fork el repositorio**
```bash
git clone https://github.com/tu-usuario/julius-mayer-simulator.git
cd julius-mayer-simulator
```

2. **Crea una rama descriptiva**
```bash
git checkout -b feature/agregar-tema-oscuro
# o
git checkout -b fix/bug-canvas-firefox
```

3. **Haz tus cambios**
- Edita los archivos necesarios
- Prueba en múltiples navegadores
- Verifica la responsividad (móvil, tablet, desktop)

4. **Commit con mensajes claros**
```bash
git add .
git commit -m "Agregar tema oscuro con toggle en header"
```

5. **Push a tu rama**
```bash
git push origin feature/agregar-tema-oscuro
```

6. **Abre un Pull Request**
- Describe los cambios claramente
- Referencia cualquier issue relacionado (#123)
- Explica por qué estos cambios son necesarios

## 📝 Estándares de Código

### JavaScript
```javascript
// ✅ Bueno
function calculateCarnorEfficiency(hotTemp, coldTemp) {
    const efficiency = ((hotTemp - coldTemp) / hotTemp) * 100;
    return efficiency.toFixed(2);
}

// ❌ Evitar
function calc(h,c){return(h-c)/h*100}
```

### CSS
```css
/* ✅ Bueno */
.simulator-control {
    margin-bottom: 20px;
    display: flex;
    gap: 10px;
}

/* ❌ Evitar */
.sim{margin:20px;display:flex;}
```

### HTML
```html
<!-- ✅ Bueno -->
<button id="submit-quiz" class="btn btn-primary" aria-label="Enviar respuestas">
    Enviar
</button>

<!-- ❌ Evitar -->
<button onclick="check()">OK</button>
```

## 🎨 Directrices de Diseño

- Mantener la paleta de colores: #667eea (principal), #764ba2 (secundario)
- Usar gradientes coherentes
- Asegurar contraste WCAG AA (4.5:1 para texto)
- Mobile-first responsive design
- Máximo 3 niveles de jerarquía de títulos

## ✅ Checklist Pre-Envío

Antes de hacer push:

- [ ] El código está limpio y bien comentado
- [ ] Probé en Chrome, Firefox y Safari
- [ ] Probé en dispositivos móviles
- [ ] No hay errores en la consola
- [ ] Las imágenes se cargan correctamente
- [ ] El layout es responsive
- [ ] Los cambios se alinean con la visión del proyecto
- [ ] Actualicé README.md si es necesario
- [ ] Los commits tienen mensajes descriptivos

## 🧪 Pruebas

Aunque este es un proyecto simple sin un framework de testing, prueba:

1. **Funcionalidad**: ¿Funcionan todos los simuladores?
2. **Navegadores**: Chrome, Firefox, Safari, Edge
3. **Dispositivos**: Desktop, tablet, móvil
4. **Rendimiento**: ¿Carga rápido?
5. **Accesibilidad**: ¿Es navegable con teclado?

## 📱 Pruebas de Responsividad

Usa las siguientes resoluciones:
- Desktop: 1920x1080, 1366x768, 1024x768
- Tablet: 768x1024, 834x1112
- Móvil: 375x667, 414x896, 320x568

## 🎯 Tipos de Contribuciones Bienvenidas

### Alto Impacto
- Nuevos simuladores
- Correcciones de bugs críticos
- Mejoras de rendimiento

### Medio Impacto
- Mejoras de UI/UX
- Documentación
- Optimizaciones de código

### Bajo Impacto
- Typos
- Ajustes de estilos menores
- Comentarios en código

## 📚 Recursos Útiles

- [MDN - Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [W3C - Responsive Design](https://www.w3.org/WAI/tutorials/page-layout/)
- [Git Guide](https://git-scm.com/doc)
- [GitHub Pull Requests](https://docs.github.com/en/pull-requests)

## 💡 Cómo Empezar

1. Revisa los [issues abiertos](https://github.com/tu-usuario/julius-mayer-simulator/issues)
2. Busca etiquetas `good-first-issue` o `help-wanted`
3. Comenta en el issue diciendo que trabajarás en ello
4. Sigue el proceso de Pull Request

## 🏆 Créditos

Todos los contribuidores serán listados en el README.md bajo la sección de "Agradecimientos".

## ❓ Preguntas

Si tienes preguntas:
- Abre una "Discussion" en GitHub
- Crea un issue con la etiqueta `question`
- Envía un email a: soporte@example.com

## 📖 Comandos Útiles

```bash
# Ver estado de cambios
git status

# Ver diferencias
git diff

# Ver historial
git log --oneline

# Descartar cambios
git checkout -- archivo.html

# Actualizar rama con cambios del upstream
git pull upstream main
```

## 🚀 Después de tu Contribución

1. Tu PR será revisado por los maintainers
2. Podem solicitar cambios o mejoras
3. Una vez aprobado, se mergeará a main
4. ¡Serás creditado en la próxima release!

---

**¡Gracias por contribuir a hacer este proyecto mejor!** 🎉
