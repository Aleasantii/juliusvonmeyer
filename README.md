# Julius Robert Mayer - Simulador Interactivo

Una página web educativa interactiva sobre **Julius Robert Mayer** y sus contribuciones revolucionarias a la termodinámica y la física moderna.

![Banner](https://via.placeholder.com/1200x300?text=Julius+Robert+Mayer+Simulator)

## 📖 Descripción

Este proyecto presenta una plataforma educativa completa sobre Julius Robert Mayer (1814-1878), el físico alemán que descubrió el equivalente mecánico del calor y propuso la ley de conservación de la energía.

**Características principales:**
- 🧬 **Biografía interactiva** con cronología de vida
- 📚 **Teorías científicas** explicadas de forma clara
- 🎮 **3 simuladores interactivos** de sus teorías
- ✅ **Test de conocimiento** con 6 preguntas
- 📱 **Diseño responsive** para desktop y móvil
- 🎨 **Interfaz moderna** con gradientes y animaciones

## 🚀 Características

### 1. Sección de Biografía
- Información detallada sobre la vida de Mayer
- Línea temporal interactiva con 8 eventos clave
- Logros principales y contribuciones científicas
- Imagen histórica

### 2. Teorías Científicas
- **Ley de Conservación de la Energía** (1842)
- **Equivalente Mecánico del Calor**: 1 cal = 4.186 J
- **Ciclo de Carnot** y su relación con Mayer
- **Imposibilidad del Movimiento Perpetuo**
- **Propiedades de Gases Ideales**

### 3. Simuladores Interactivos

#### Simulador 1: Equivalente Mecánico del Calor
- Convierte trabajo mecánico (J) en calor (cal)
- Gráfico dinámico en tiempo real
- Rango: 0-1000 julios

#### Simulador 2: Expansión Adiabática de Gas
- Simula la expansión de un gas ideal
- Muestra cambios de temperatura
- Visualización del proceso termodinámico

#### Simulador 3: Ciclo de Carnot
- Calcula eficiencia máxima de motores térmicos
- Variación de temperaturas (K)
- Fórmula: η = 1 - (T_fría / T_caliente)

### 4. Test de Conocimiento
- 6 preguntas sobre Mayer y sus teorías
- Retroalimentación automática
- Cálculo de porcentaje de aciertos

## 💻 Requisitos Técnicos

- Navegador web moderno (Chrome, Firefox, Safari, Edge)
- JavaScript habilitado
- Resolución mínima: 320px (mobile-friendly)

**No requiere:**
- Instalación de software
- Backend o servidor
- Conexión a internet (después de cargar)

## 📥 Instalación

### Opción 1: Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/julius-mayer-simulator.git
cd julius-mayer-simulator
```

### Opción 2: Descarga directa
1. Descarga el archivo `index.html`
2. Abre en tu navegador

## 🎯 Uso

1. **Abre `index.html`** en tu navegador
2. **Navega** entre las secciones usando los botones superiores:
   - 📖 Biografía
   - 📚 Teorías
   - 🎮 Simulador
   - ✅ Test
3. **Interactúa** con los simuladores moviendo los controles deslizantes
4. **Responde** el test para evaluar tu conocimiento

## 📱 Responsividad

La página está optimizada para:
- ✅ Desktop (1200px+)
- ✅ Tablet (768px - 1199px)
- ✅ Móvil (320px - 767px)

## 🎨 Tecnologías Utilizadas

- **HTML5**: Estructura semántica
- **CSS3**: Estilos, gradientes, flexbox, grid
- **JavaScript (Vanilla)**: Interactividad sin dependencias
- **Canvas API**: Gráficos y simuladores
- **Responsive Design**: Mobile-first

## 📊 Estructura del Proyecto

```
julius-mayer-simulator/
│
├── index.html              # Archivo principal (HTML + CSS + JS)
├── README.md              # Este archivo
├── .gitignore             # Configuración de Git
└── assets/                # (Opcional) Para imágenes locales
    ├── mayer.jpg
    └── biografía-resumen.txt
```

## 🔬 Conceptos Científicos Implementados

### Equivalente Mecánico del Calor
```
E (Energía Mecánica) = Q (Calor) × 4.186
1 caloría = 4.186 julios
```

### Ley de Conservación de la Energía
```
E_inicial = E_final
La energía no se crea ni se destruye, solo se transforma
```

### Eficiencia del Ciclo de Carnot
```
η = 1 - (T_fría / T_caliente) × 100%
Donde T está en Kelvin
```

### Proceso Adiabático
```
T × V^(γ-1) = constante
Donde γ (gamma) ≈ 1.4 para aire
```

## 📚 Referencias Históricas

- **Descubrimiento clave**: 1842 - Equivalente mecánico del calor
- **Publicaciones**: 20+ trabajos sobre energía y termodinámica
- **Reconocimiento tardío**: Ganó aceptación científica en 1860+
- **Legado**: Fundamentó el 1er Principio de la Termodinámica

## 🎓 Usos Educativos

Ideal para:
- Estudiantes de secundaria y universidad
- Profesores de física y termodinámica
- Curiosos sobre historia de la ciencia
- Preparación de exámenes
- Trabajos de investigación

## 🐛 Problemas Conocidos

- Los gráficos en Canvas pueden no verse óptimamente en navegadores muy antiguos
- En conexiones lentas, las imágenes externas (Wikipedia) pueden tardar

## 🤝 Contribuciones

Las contribuciones son bienvenidas! Para proponer cambios:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

### Áreas para mejorar:
- [ ] Agregar más simuladores
- [ ] Animaciones CSS mejoradas
- [ ] Tema oscuro
- [ ] Soporte para múltiples idiomas
- [ ] Videos educativos integrados
- [ ] Descargar resultados de simuladores

## 📝 Licencia

Este proyecto está bajo licencia **MIT** - ver el archivo `LICENSE` para más detalles.

```
MIT License

Copyright (c) 2024 [Tu Nombre]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

## 👤 Autor

**Tu Nombre**
- GitHub: [@tu-usuario](https://github.com/tu-usuario)
- Email: tu-email@example.com

## 🙏 Agradecimientos

- Imágenes históricas de Wikimedia Commons
- Inspirado en recursos educativos abiertos
- Comunidad de desarrolladores web

## 📞 Contacto y Soporte

- 📧 Email: soporte@example.com
- 🐦 Twitter: [@tu-twitter](https://twitter.com/tu-twitter)
- 💬 Issues: [GitHub Issues](https://github.com/tu-usuario/julius-mayer-simulator/issues)

## 🗺️ Roadmap

### v1.1 (Próximo)
- [ ] Tema oscuro automático
- [ ] Exportar resultados en PDF
- [ ] Más gráficos interactivos

### v2.0 (Futuro)
- [ ] Modo offline con Service Workers
- [ ] Multiplayer: Competir en tests
- [ ] Integración con plataformas LMS
- [ ] Contenido en otros idiomas

## 📈 Estadísticas

- **Líneas de código**: ~1500
- **Tamaño del archivo**: ~180 KB
- **Secciones**: 4
- **Simuladores**: 3
- **Preguntas de test**: 6
- **Tiempo de carga**: < 2 segundos

## 🔗 Enlaces Relacionados

- [Biografía de Mayer - Wikipedia](https://en.wikipedia.org/wiki/Julius_Robert_von_Mayer)
- [Termodinámica - Khan Academy](https://www.khanacademy.org)
- [Historia de la Física](https://www.physicshistory.org)

---

**Última actualización**: 2024
**Versión**: 1.0.0
**Estado**: ✅ Estable
