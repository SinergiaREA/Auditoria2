# 📊 NIA 700 — Evaluación de Auditoría

Una herramienta interactiva diseñada para evaluar conocimientos sobre la **Norma Internacional de Auditoría 700** (NIA 700), con enfoque en la evaluación y componentes del informe del auditor independiente.

## 🎯 Descripción

Aplicación web responsiva que proporciona una evaluación diagnóstica completa sobre NIA 700. Diseñada específicamente para **Contaduría Pública · Auditoría II**, ofrece feedback inmediato y generación de reportes PDF profesionales.

### Público objetivo
- Estudiantes de auditoría y contabilidad
- Profesionales en formación contable
- Auditores internos y externos
- Preparación para exámenes de normas internacionales

## ✨ Características principales

| Función | Descripción |
|---------|------------|
| **14 preguntas** | Evaluación completa y fundamentada en NIA 700 |
| **Tiempo límite** | 30 segundos por pregunta para mayor dinamismo |
| **Retroalimentación inmediata** | Explicaciones detalladas después de cada respuesta |
| **Sistema de rachas** | Indicador de respuestas consecutivas correctas 🔥 |
| **Sesión persistente** | localStorage para recuperar progreso si se recarga |
| **Sistema de calificaciones** | Escala A-F con mensajes motivacionales personalizados |
| **Reporte PDF** | Descarga de resultados completos con detalles de respuestas |
| **Confetti visual** | Celebración animada al alcanzar calificación aprobatoria |
| **Validación de seguridad** | Sanitización de inputs y headers HTTP protegidos |

## 🎨 Diseño y UX

### Componentes visuales
- **Tipografía premium**: Playfair Display (títulos elegantes), DM Sans (interfaz clara), DM Mono (etiquetas técnicas)
- **Paleta de colores profesional**:
  - 🟡 **Oro** (#c9a84c) — Acentos y destacados
  - 🟢 **Esmeralda** (#0f7b52) — Respuestas correctas
  - 🔴 **Rubí** (#c0392b) — Errores y alertas
  - 🔵 **Zafiro** (#1a5f9e) — Información secundaria
  - 🟠 **Ámbar** (#d97706) — Advertencias
- **Efecto de ruido sutil** para mayor refinamiento visual
- **Animaciones suaves** en transiciones y feedback

### Responsive
Funciona perfectamente en:
- Desktop (1280px+)
- Tablets (768px - 1279px)
- Móviles (320px - 767px)

## 🚀 Inicio rápido

### Opción 1: Directo en navegador
```bash
1. Descarga el archivo dinamica-auditoria.html
2. Haz doble clic para abrir en tu navegador por defecto
3. ¡Comienza la evaluación!
```

### Opción 2: Servidor local (recomendado para PDF)
```bash
# Con Python 3
python -m http.server 8000

# Con Node.js
npx http-server

# Luego abre: http://localhost:8000/dinamica-auditoria.html
```

## 📋 Flujo de uso

```
┌─────────────────────────────────────┐
│   PANTALLA 1: Login                 │
│   Ingresa tu nombre completo        │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   PANTALLA 2: Quiz                  │
│   • Pregunta + 4 opciones          │
│   • Timer: 30 segundos             │
│   • Feedback inmediato             │
│   • Racha de aciertos             │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   PANTALLA 3: Resultados           │
│   • Calificación y porcentaje      │
│   • Gráfico de progreso            │
│   • Revisión de respuestas         │
│   • Descarga PDF                   │
└─────────────────────────────────────┘
```

## 📝 Contenido temático

La evaluación abarca **13 elementos estructurados de NIA 700**:

1. **Título del informe** — Inclusión de "Independiente"
2. **Opinión del auditor** — Prioridad y ubicación
3. **Fundamento de la opinión** — Descripción de procedimientos
4. **Responsabilidades** — Usuario final vs. administración
5. **Información financiera** — Alcance y período
6. **Tipos de opinión** — Sin salvedades, con salvedades, adversa, abstención
7. **Cuestiones Clave de Auditoría** — Aplicabilidad por tipo de entidad
8. **Escepticismo profesional** — Actitud crítica del auditor
9. **Materialidad** — Concepto y aplicación
10. **Fecha del informe** — Restricciones temporales
11. **Seguridad razonable** — Nivel de certeza proporcionado

## 💻 Requisitos técnicos

| Requisito | Mínimo | Recomendado |
|-----------|--------|------------|
| **Navegador** | Chrome 60+, Firefox 55+, Safari 11+, Edge 79+ | Versión actual |
| **JavaScript** | ES6 habilitado | Soportado |
| **RAM** | 256 MB | 512 MB+ |
| **Conexión** | No requiere internet* | Necesario para PDF |

*El PDF requiere CDN: jsPDF y html2canvas

## 🔒 Medidas de seguridad

### Headers HTTP
```
X-Content-Type-Options: nosniff       → Evita MIME sniffing
X-Frame-Options: DENY                 → Previene clickjacking
Referrer-Policy: no-referrer          → Protege privacidad
```

### Validación de datos
- Sanitización de HTML (escape de caracteres especiales)
- Validación de nombres: solo letras, espacios y acentos (2-80 caracteres)
- Sin almacenamiento de datos personales en servidor
- localStorage local del navegador (privado)

## 📊 Sistema de calificación

| Porcentaje | Letra | Descripción | Icono |
|-----------|-------|------------|-------|
| 90-100% | A | Dominio sobresaliente | 🏆 |
| 80-89% | B | Muy buen desempeño | 🥈 |
| 70-79% | C | Resultado aceptable | 🎗️ |
| 60-69% | D | Necesita repasar | 📚 |
| < 60% | F | Oportunidad de mejora | 📖 |

## 📥 Exportar resultados

### Función PDF
- Genera reporte profesional con:
  - Datos del estudiante y fecha
  - Calificación y porcentaje
  - Análisis completo de cada pregunta
  - Explicaciones de conceptos
  - Nombre del docente en pie de página

### Nombre del archivo
`NIA700_[Nombre]_[Fecha].pdf`

## 🔧 Personalización

### Editar preguntas
Localiza el array `QS` en el script:
```javascript
const QS=[
  {q:"Tu pregunta aquí",
   o:["Opción A","Opción B","Opción C","Opción D"],
   c:1,  // índice de respuesta correcta (0-3)
   exp:"Explicación detallada..."}
]
```

### Cambiar tiempo de pregunta
Busca `const TOTAL_TIME=30` y reemplaza con tu valor.

### Modificar colores
Edita las variables CSS en `:root`:
```css
--gold: #c9a84c;
--emerald: #0f7b52;
/* etc */
```

## 📱 Compatibilidad

| Navegador | Desktop | Tablet | Móvil |
|-----------|---------|--------|-------|
| Chrome | ✅ | ✅ | ✅ |
| Firefox | ✅ | ✅ | ✅ |
| Safari | ✅ | ✅ | ✅ |
| Edge | ✅ | ✅ | ✅ |
| IE 11 | ❌ | ❌ | ❌ |

## 📚 Referencias normativas

- **NIA 700** — Formación de una opinión y emisión de informe sobre estados financieros
- **IFAC** — Federación Internacional de Contadores
- **INTOSAI** — Organización Internacional de Entidades Fiscalizadoras Superiores
- Normativas locales según jurisdicción

## 🤝 Contacto y soporte

**Docente responsable**
- Mtra. Jaquelina Judith Sánchez Antele
- Materia: Auditoría II
- Programa: Contaduría Pública

## 📄 Licencia y términos

- **Tipo**: Uso educativo interno exclusivamente
- **Prohibido**: Comercialización, distribución sin autorización
- **Datos**: No se recopilan ni transmiten datos personales (almacenamiento local)

---

**Última actualización**: Febrero 2026 | **Versión**: 2.0
