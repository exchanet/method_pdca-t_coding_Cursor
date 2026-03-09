# Método PDCA-T — Framework de Calidad para Codificación con IA

> **Una metodología sistemática multi-agente para desarrollo asistido por IA que garantiza ≥99% de cobertura de tests, cero vulnerabilidades, cero bugs en producción y entrega completamente documentada.**

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Versión](https://img.shields.io/badge/versi%C3%B3n-3.0.0-blue.svg)]()
[![Agente: cualquiera](https://img.shields.io/badge/agente-cualquiera-green.svg)]()
[![Idioma: ES/EN](https://img.shields.io/badge/Idioma-ES%2FEN-blue.svg)](./README.md)

**Autor:** Francisco J. Bernades ([@exchanet](https://github.com/exchanet))  
**Repositorio:** [github.com/exchanet/method_pdca-t_coding](https://github.com/exchanet/method_pdca-t_coding)

---

## 🎯 Resumen

El **Método PDCA-T** es un flujo de trabajo completo para desarrollo asistido por IA con **cualquier agente** (Cursor, Windsurf, GitHub Copilot, Claude Code, Claude.ai, ChatGPT, Aider, etc.). Transforma tareas de codificación en procesos sistemáticos y validados que aseguran:

- ✅ **≥99% de cobertura de tests** en todo el código
- ✅ **Cero vulnerabilidades** mediante prácticas de seguridad primero
- ✅ **Cero bugs en producción** mediante pruebas exhaustivas de casos límite
- ✅ **Transparencia total** con reportes detallados de tests
- ✅ **Arquitectura antes que código** — ADRs y contratos de interfaz
- ✅ **Funciona con cualquier agente** — hay un adapter en la carpeta `adapters/` para cada uno
- ✅ **Funciona con cualquier stack** — Python, Node.js, Go, TypeScript, etc.

El método es **uno solo, en 8 fases**. La especificación técnica bilingüe (EN/ES) está en [METHOD.md](METHOD.md).

---

> **¿Quieres sistemas completos listos para producción?**  
> El Método PDCA-T se ocupa de la calidad, los tests y la validación sistemática.  
> Para arquitectura modular con Admin Panels auto-generados, úsalo junto a **[Method Modular Design](https://github.com/exchanet/method_modular_design)**.  
> *Modular Design construye el sistema correcto. PDCA-T lo construye bien.*

---

## 🚀 Inicio Rápido

### Instalación — 3 opciones

**Opción 1 — enet (recomendado)**

[`enet`](https://github.com/exchanet/enet) es el gestor de métodos de exchanet. Detecta tu agente de IA automáticamente e instala el adapter en el lugar correcto.

```bash
npm install -g @exchanet/enet
enet install pdca-t
```

**Opción 2 — enet vía GitHub (sin cuenta npm)**

```bash
npm install -g github:exchanet/enet
enet install pdca-t
```

**Opción 3 — Manual**

Descarga el adapter para tu agente desde la carpeta `adapters/`:

| Agente | Archivo | Dónde colocarlo |
|--------|---------|-----------------|
| Cursor | `adapters/cursor.md` | `.cursor/rules/method-pdca-t.md` |
| Windsurf | `adapters/windsurf.md` | Añadir al final de `.windsurfrules` |
| GitHub Copilot | `adapters/copilot.md` | `.github/copilot-instructions.md` |
| Claude Code | `adapters/claudecode.md` | `CLAUDE.md` |
| Claude.ai | `adapters/claudeai.md` | Pegar en system prompt o conversación |
| ChatGPT / GPT-4o | `adapters/openai.md` | Pegar en instrucciones personalizadas |
| Aider | `adapters/aider.md` | Flag `--system-prompt` o `.aider.conf.yml` |
| Cualquier otro agente | `adapters/generic.md` | Pegar en el contexto de tu agente |

Para **Cursor** además puedes copiar la regla y la skill del repo:

```bash
cp .cursor/rules/METHOD-PDCA-T.md /ruta/a/tu/proyecto/.cursor/rules/
cp -r .cursor/skills/method-pdca-t /ruta/a/tu/proyecto/.cursor/skills/
```

---

## 📖 El Método Explicado

### Por Qué Este Método Funciona

Los flujos de trabajo de codificación tradicionales a menudo omiten la validación o la realizan como una idea tardía. El método PDCA-T **integra el aseguramiento de calidad en cada paso**, asegurando que:

1. **La planificación previene el crecimiento del alcance** - Objetivos y requisitos claros desde el principio
2. **Las micro-tareas permiten el enfoque** - Máximo 50 líneas por tarea asegura minuciosidad
3. **La validación inmediata detecta errores temprano** - Tests escritos y ejecutados antes de continuar
4. **El 99% de cobertura elimina sorpresas** - Casos límite descubiertos durante el desarrollo, no en producción
5. **El enfoque de seguridad primero previene vulnerabilidades** - Validación de inputs y sanitización de outputs desde el primer día

### El ciclo completo (8 fases)

El método es uno solo, en **8 fases**. La especificación técnica bilingüe está en [METHOD.md](METHOD.md).

```
FASE 1: PLANIFICACIÓN
│
▼
FASE 2: ANÁLISIS DE REQUISITOS
│
▼
FASE 3: DISEÑO DE ARQUITECTURA (ADRs, contratos de interfaz)
│
▼
FASE 4: CICLO DE MICRO-TAREAS (por cada tarea ≤ 50 líneas)
│  ┌─────────────────────────────────────────────────┐
│  │ 4.1 Verificar skills y contexto                  │
│  │ 4.2 Escribir tests PRIMERO (TDD)                │
│  │ 4.3 Implementar (≤ 50 líneas)                   │
│  │ 4.4 Auto-revisión                               │
│  │ 4.5 Ejecutar tests — mostrar resultado REAL     │
│  │ 4.6 Si cobertura < 99% → refinar y repetir      │
│  └─────────────────────────────────────────────────┘
│
▼
FASE 5: VALIDACIÓN INTEGRAL CON MÉTRICAS
│
▼
FASE 6: GESTIÓN DE DEUDA TÉCNICA (DEBT-XXX / DEUDA-XXX)
│
▼
FASE 7: REFINAMIENTO HASTA ≥99%
│
▼
FASE 8: ENTREGA CON REPORTE COMPLETO
```

---

## 📚 Desglose Detallado de Fases

### Fase 1: Planificación

**Propósito:** Establecer una comprensión clara de lo que hay que hacer.

**Acciones:**
- Analiza el objetivo general
- Identifica el alcance exacto
- Pregunta si algo no está claro
- **Output:** Comprensión clara de la tarea

**Por qué importa:** Sin planificación clara, perderás tiempo corrigiendo malentendidos después. Esta fase asegura alineación desde el inicio.

---

### Fase 2: Análisis de Requisitos

**Propósito:** Identificar todos los requisitos funcionales y no funcionales, además de riesgos potenciales.

**Acciones:**
- Identifica requisitos funcionales (qué debe hacer el código)
- Identifica requisitos no funcionales (seguridad, rendimiento, escalabilidad)
- Identifica riesgos potenciales
- **Output:** Lista completa de requisitos y riesgos

**Por qué importa:** Perder un requisito no funcional (como "debe manejar 10k solicitudes/seg") lleva a refactorización costosa. Esta fase los detecta temprano.

---

### Fase 3: Diseño de Arquitectura

**Propósito:** Dejar documentadas las decisiones de arquitectura antes de implementar.

**Acciones:**
- Escribir ADRs (Architecture Decision Records)
- Definir contratos de interfaz (firmas y docstrings) antes del código
- Definir estructura de módulos: dominio / infraestructura / interfaces

**Por qué importa:** Evita refactorizaciones costosas y mantiene coherencia. La especificación completa está en [METHOD.md](METHOD.md).

---

### Fase 4: Ciclo de Micro-Tareas

**Propósito:** Implementar en fragmentos manejables de máximo 50 líneas cada uno.

**¿Por qué 50 líneas?**
- Más fácil de revisar minuciosamente
- Más fácil de testear completamente
- Más fácil de depurar si surgen problemas
- Fuerza diseño modular con responsabilidad única

**Para cada micro-tarea, ejecuta este sub-ciclo:**

#### 4.1 Verificar skills y contexto disponibles

Antes de escribir código, verifica si hay una skill o contexto reutilizable que pueda ayudar (en Cursor: `.cursor/skills/`; en otros agentes, el equivalente en su sistema de reglas o instrucciones). Las skills proporcionan conocimiento especializado y flujos de trabajo.

**Ejemplo:** Si construyes un componente React, verifica si existe una skill de frontend o diseño.

#### 4.2 Ejecutar la tarea

Escribe código siguiendo:
- Type hints completos (Python 3.12+ o TypeScript)
- Buenas prácticas de seguridad
- Cero hardcoding (todo configurable)
- Manejo específico de excepciones
- Logging estructurado

#### 4.3 Auto-revisión inmediata

Revisa el código que acabas de escribir:
- ✅ ¿Tiene type hints?
- ✅ ¿Hay vulnerabilidades de seguridad?
- ✅ ¿Hay duplicación de código?
- ✅ ¿Es legible y mantenible?
- ✅ ¿Sigue las mejores prácticas del lenguaje?

**¿Por qué inmediata?** Detectar problemas justo después de escribir es 10 veces más fácil que días después.

#### 4.4 Generar tests completos

Escribe tests unitarios que cubran:

**Mínimo Requerido:**
- [ ] Test de caso feliz (operación normal)
- [ ] Test de caso de error (validación, excepciones)
- [ ] Test de caso límite (condiciones de frontera)
- [ ] Test de valores frontera
- [ ] Test de entrada inválida
- [ ] Test de seguridad (inyección, permisos)
- [ ] Test de rendimiento (si aplica)

**Estructura de Ejemplo:**
```python
def test_funcionalidad_happy_path():
    """Prueba que la funcionalidad funciona con inputs válidos."""
    # Arrange
    input_data = crear_input_valido()
    # Act
    resultado = funcionalidad(input_data)
    # Assert
    assert resultado.es_valido()
    assert resultado.valor == valor_esperado

def test_funcionalidad_error():
    """Prueba que lanza error correcto con inputs inválidos."""
    with pytest.raises(ValidationError):
        funcionalidad(input_invalido)

def test_funcionalidad_edge_case():
    """Prueba casos límite (valores mínimos, máximos, vacíos, etc)."""
    # Test de entrada vacía
    resultado = funcionalidad(input_vacio)
    assert resultado == valor_por_defecto
```

#### 4.5 Ejecutar tests y mostrar resultados

**OBLIGATORIO:** Ejecuta tests y muestra:
- Número total de tests ejecutados
- Cuántos pasaron
- Cuántos fallaron
- Cuántos están pendientes

**Ejemplo de Salida:**
```bash
$ pytest tests/test_modulo.py -v

tests/test_modulo.py::test_happy_path PASSED
tests/test_modulo.py::test_error_case PASSED
tests/test_modulo.py::test_edge_case PASSED
tests/test_modulo.py::test_security PASSED

4 passed, 0 failed, 0 skipped
```

**¿Por qué mostrar resultados?** La transparencia genera confianza y ayuda a identificar problemas inmediatamente.

#### 4.6 Validar cobertura y calidad

- ¿Todos los tests pasan (100%)?
- ¿Cobertura estimada ≥99%?
- ¿Hay casos no cubiertos?

**Si cobertura < 99% o tests fallando:**
1. Identifica qué falta
2. Mejora código o tests
3. Repite desde 4.4 hasta alcanzar ≥99%

**¿Por qué 99%?** El 100% a menudo es impracticable (manejadores de error, código inalcanzable), pero el 99% asegura que todas las rutas críticas estén testeadas.

---

### Fase 5: Validación Integral con Métricas

Después de completar todas las micro-tareas, genera un reporte con las cinco dimensiones (seguridad, tests, calidad de código, rendimiento, arquitectura):

#### 1. Validación de Seguridad
- [ ] Sin vulnerabilidades críticas
- [ ] Validación de inputs en todos los endpoints
- [ ] Sanitización de outputs
- [ ] Sin secrets hardcodeados
- [ ] Permisos RBAC correctamente aplicados

#### 2. Validación de Tests
- **Total de tests ejecutados:** [XX]
- **Tests pasados:** [XX] (100%)
- **Tests fallados:** [0]
- **Cobertura estimada:** [≥99%]
- **Casos cubiertos:** Happy path, error, edge cases, seguridad

#### 3. Validación de Calidad de Código
- [ ] Type hints: 100% de cobertura
- [ ] Complejidad ciclomática < 10 por función
- [ ] Sin duplicación de código
- [ ] Nombres de variables semánticos
- [ ] Funciones con responsabilidad única

#### 4. Validación de Rendimiento
- [ ] Sin consultas N+1
- [ ] Índices adecuados en consultas frecuentes
- [ ] Paginación en listados
- [ ] Timeouts configurados

#### 5. Validación de Arquitectura
- [ ] Sin importaciones circulares
- [ ] Capas respetadas
- [ ] Módulos sin acoplamiento indebido

---

### Fase 6: Gestión de Deuda Técnica

Registra todo problema conocido antes de entregar en formato DEBT-XXX (o DEUDA-XXX en la sección ES de METHOD.md): tipo, descripción, impacto, esfuerzo, prioridad y plan. No dejes TODO/FIXME en el código; regístralos como deuda. Detalle en [METHOD.md](METHOD.md).

---

### Fase 7: Refinamiento hasta ≥99%

Si alguna métrica no alcanza el 99%:

1. **Identifica el problema** - ¿Qué falta?
2. **Evalúa el impacto** - Alto/Medio/Bajo
3. **Define acción correctiva** - ¿Qué harás?
4. **Implementa la corrección** - Realiza los cambios
5. **Re-ejecuta tests** - Verifica la corrección
6. **Confirma cobertura ≥99%** - ¿Objetivo alcanzado?

**¿Por qué iterar?** La perfección no se logra en el primer intento. Esta fase asegura que alcances el estándar de calidad.

---

### Fase 8: Entrega con Reporte Completo

Genera un reporte final con:

- **Resumen de Implementación** (2-3 líneas describiendo qué se implementó)
- **Reporte de Tests:**
  - Total tests: XX
  - Pasados: XX (100%)
  - Fallados: 0
  - Cobertura: ≥99%
- **Ejecución Detallada** (salida completa de pytest)
- **Decisiones Clave** (con justificaciones)
- **Próximos Pasos Sugeridos**

**¿Por qué documentar decisiones?** Los desarrolladores futuros (incluyéndote a ti) entenderán por qué se tomaron las decisiones.

---

## 🔒 Reglas Absolutas (No Negociables)

### 1. Tests Obligatorios
- Toda función DEBE tener tests
- Los tests DEBEN ejecutarse y mostrarse
- La cobertura DEBE ser ≥99%

### 2. Seguridad Primero
- Nunca expongas información sensible
- Siempre valida inputs
- Siempre sanitiza outputs

### 3. Cero Vulnerabilidades
- Sin inyección SQL
- Sin secrets hardcodeados
- Sin exposición de datos sensibles

### 4. Cero Bugs en Producción
- Cada línea debe tener propósito
- Cada función debe tener tests
- Cada caso límite debe considerarse
- Validación ≥99% antes de entregar

### 5. Transparencia Total
- Siempre muestra resultados de tests
- Explica decisiones técnicas
- Pregunta cuando tengas dudas
- Reporta problemas encontrados

---

## 📁 Estructura del Repositorio

```
method_pdca-t_coding/
├── adapters/                          # Un adapter por agente (Cursor, Windsurf, Copilot, Claude, etc.)
│   ├── cursor.md
│   ├── windsurf.md
│   ├── copilot.md
│   ├── claudecode.md
│   ├── claudeai.md
│   ├── openai.md
│   ├── aider.md
│   └── generic.md
├── .cursor/                           # Para Cursor: regla + skill
│   ├── rules/
│   │   └── METHOD-PDCA-T.md
│   └── skills/
│       └── method-pdca-t/
│           └── SKILL.md
├── docs/
│   ├── INSTALLATION.md
│   ├── USAGE.md
│   └── ALINEACION-EN-ES.md
├── examples/
├── METHOD.md                          # Especificación técnica (8 fases, EN + ES)
├── README.md                          # Inglés
├── README.es.md                       # Español (este archivo)
├── README_ES.md                       # Español (espejo completo del README.md)
├── LICENSE
└── CONTRIBUTING.md
```

---

## 🎓 Ejemplos

Consulta el directorio [`examples/`](./examples/) para ejemplos de implementación del mundo real.

### Ejemplo: Implementar Calculadora de Impuestos

```
FASE 1: Planificación
→ Objetivo: Crear función de cálculo de impuestos

FASE 2: Análisis de Requisitos
→ Funcionales: Calcular IVA, IRPF
→ No funcionales: Precisión decimal, rendimiento
→ Riesgos: Errores de redondeo, valores negativos

FASE 4: Micro-tareas (ciclo por tarea)
→ Tarea 1: Función calcular_iva (50 líneas)
  → 4.1–4.6: tests primero, implementar, auto-revisión, ejecutar tests, cobertura 100% ✓

→ Tarea 2: Función calcular_irpf (50 líneas)
  → [mismo ciclo]

FASE 5: Validación Integral
→ Seguridad, tests, calidad, rendimiento, arquitectura ✓

FASE 6: Deuda técnica registrada (si aplica)
FASE 7: Refinamiento → ya ≥99%
FASE 8: Entrega
→ [Reporte completo]
```

---

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Por favor lee [CONTRIBUTING.md](./CONTRIBUTING.md) para detalles sobre nuestro código de conducta y el proceso para enviar pull requests.

---

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT - consulta el archivo [LICENSE](./LICENSE) para más detalles.

---

## 🙏 Agradecimientos

- Inspirado en la metodología PDCA (Plan-Do-Check-Act)
- Mejorado con principios de Desarrollo Dirigido por Tests
- Diseñado para desarrollo asistido por IA con cualquier agente (Cursor, Windsurf, Copilot, Claude, ChatGPT, Aider, etc.)

---

## 📞 Contacto

**Autor:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

Para preguntas, sugerencias o comentarios, por favor abre un issue en GitHub.

---

## ⭐ Por Qué Este Método Entrega Resultados Excelentes

### 1. **Previene Deuda Técnica**
Al requerir tests y validación en cada paso, detectas problemas temprano cuando son baratos de corregir.

### 2. **Asegura Seguridad**
El enfoque de seguridad primero significa que las vulnerabilidades se previenen, no se parchean después.

### 3. **Construye Confianza**
Cuando ves "100% tests pasados, 99% cobertura", sabes que el código funciona.

### 4. **Facilita Mantenimiento**
Código bien testeado y documentado es más fácil de modificar y extender.

### 5. **Escala con Complejidad**
El enfoque de micro-tareas mantiene la complejidad manejable incluso para características grandes.

### 6. **Transparencia**
Reportes completos de tests y documentación de decisiones ayudan a los equipos a colaborar efectivamente.

---

**¿Listo para codificar con confianza?** ¡Instala el método y comienza tu próxima tarea! 🚀
