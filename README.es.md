# Método PDCA-T Mejorado para Codificación en Cursor AI

> **Una metodología sistemática de codificación con garantía de calidad que asegura ≥99% de cobertura de tests y cero bugs en producción mediante ciclos de validación rigurosos.**

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Compatible con Cursor](https://img.shields.io/badge/Cursor-AI-Compatible-blue)](https://cursor.sh)

**Autor:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

---

## 🎯 Resumen

El **Método PDCA-T Mejorado para Codificación** es un flujo de trabajo completo diseñado para desarrollo asistido por IA en Cursor. Transforma tareas de codificación en procesos sistemáticos y validados que aseguran:

- ✅ **≥99% de cobertura de tests** en todo el código
- ✅ **Cero vulnerabilidades** mediante prácticas de seguridad primero
- ✅ **Cero bugs en producción** mediante pruebas exhaustivas de casos límite
- ✅ **Transparencia total** con reportes detallados de tests
- ✅ **Aseguramiento de calidad sistemático** en cada paso

Este método aplica un ciclo **Plan-Do-Check-Act-Test (PDCA-T)** mejorado con métricas de validación rigurosas, ideal para desarrollo de software de grado productivo.

---

## 🚀 Inicio Rápido

### Instalación

1. **Clona o descarga este repositorio:**
   ```bash
   git clone https://github.com/exchanet/method_pdca-t_coding_Cursor.git
   cd method_pdca-t_coding_Cursor
   ```

2. **Copia la regla a tu proyecto de Cursor:**
   ```bash
   # Copia el archivo de regla
   cp .cursor/rules/METODO-PDCA-T.md /ruta/a/tu/proyecto/.cursor/rules/
   
   # O copia toda la estructura del directorio .cursor
   cp -r .cursor /ruta/a/tu/proyecto/
   ```

3. **El método se activará automáticamente** - Cursor leerá la regla con `trigger: always_on` y la aplicará a todas las tareas.

### Alternativa: Instalar como Skill

Si prefieres usarlo como skill reutilizable:

```bash
cp -r .cursor/skills/metodo-pdca-t /ruta/a/tu/proyecto/.cursor/skills/
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

### El Ciclo Completo

```
FASE 1: PLANIFICACIÓN (Planning)
│
▼
FASE 2: ANÁLISIS DE REQUISITOS (Requirements Analysis)
│
▼
FASE 3: DIVISIÓN EN MICRO-TAREAS (Micro-Task Division)
│
▼
┌─────────────────────────────────────────────────┐
│  POR CADA MICRO-TAREA:                          │
│  ┌─────────────────────────────────────────┐    │
│  │ 3.1 Verificar skills disponibles         │    │
│  │ 3.2 Ejecutar con skill aplicada         │    │
│  │ 3.3 Auto-revisión                        │    │
│  │ 3.4 Generar tests COMPLETOS              │    │
│  │ 3.5 EJECUTAR tests y mostrar resultado   │    │
│  │ 3.6 Si cobertura < 99% → revisar y mejorar│    │
│  └─────────────────────────────────────────┘    │
└─────────────────────────────────────────────────┘
│
▼
FASE 4: VALIDACIÓN INTEGRAL CON MÉTRICAS (Integral Validation)
│
▼
FASE 5: REFINAMIENTO HASTA ≥99% (Refinement to ≥99%)
│
▼
FASE 6: ENTREGA CON REPORTE DE TESTS (Delivery with Test Report)
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

### Fase 3: División en Micro-Tareas

**Propósito:** Dividir el trabajo en fragmentos manejables de máximo 50 líneas cada uno.

**¿Por qué 50 líneas?**
- Más fácil de revisar minuciosamente
- Más fácil de testear completamente
- Más fácil de depurar si surgen problemas
- Fuerza diseño modular con responsabilidad única

**Para cada micro-tarea, ejecuta este sub-ciclo:**

#### 3.1 Verificar Skills Disponibles

Antes de escribir código, verifica si hay una skill relevante en `.cursor/skills/` que pueda ayudar. Las skills proporcionan conocimiento especializado y flujos de trabajo.

**Ejemplo:** Si construyes un componente React, verifica la skill `frontend-design`.

#### 3.2 Ejecutar la Tarea

Escribe código siguiendo:
- Type hints completos (Python 3.12+ o TypeScript)
- Buenas prácticas de seguridad
- Cero hardcoding (todo configurable)
- Manejo específico de excepciones
- Logging estructurado

#### 3.3 Auto-Revisión Inmediata

Revisa el código que acabas de escribir:
- ✅ ¿Tiene type hints?
- ✅ ¿Hay vulnerabilidades de seguridad?
- ✅ ¿Hay duplicación de código?
- ✅ ¿Es legible y mantenible?
- ✅ ¿Sigue las mejores prácticas del lenguaje?

**¿Por qué inmediata?** Detectar problemas justo después de escribir es 10 veces más fácil que días después.

#### 3.4 Generar Tests Completos

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

#### 3.5 Ejecutar Tests y Mostrar Resultados

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

#### 3.6 Validar Cobertura y Calidad

- ¿Todos los tests pasan (100%)?
- ¿Cobertura estimada ≥99%?
- ¿Hay casos no cubiertos?

**Si cobertura < 99% o tests fallando:**
1. Identifica qué falta
2. Mejora código o tests
3. Repite desde 3.4 hasta alcanzar ≥99%

**¿Por qué 99%?** El 100% a menudo es impracticable (manejadores de error, código inalcanzable), pero el 99% asegura que todas las rutas críticas estén testeadas.

---

### Fase 4: Validación Integral con Métricas

Después de completar todas las micro-tareas, genera un reporte completo:

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

### Fase 5: Refinamiento hasta ≥99%

Si alguna métrica no alcanza el 99%:

1. **Identifica el problema** - ¿Qué falta?
2. **Evalúa el impacto** - Alto/Medio/Bajo
3. **Define acción correctiva** - ¿Qué harás?
4. **Implementa la corrección** - Realiza los cambios
5. **Re-ejecuta tests** - Verifica la corrección
6. **Confirma cobertura ≥99%** - ¿Objetivo alcanzado?

**¿Por qué iterar?** La perfección no se logra en el primer intento. Esta fase asegura que alcances el estándar de calidad.

---

### Fase 6: Entrega con Reporte de Tests

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
method_pdca-t_coding_Cursor/
├── .cursor/
│   ├── rules/
│   │   └── METODO-PDCA-T.md          # Regla de Cursor (se activa automáticamente)
│   └── skills/
│       └── metodo-pdca-t/
│           └── SKILL.md              # Skill reutilizable
├── docs/
│   ├── INSTALLATION.md               # Guía de instalación
│   ├── USAGE.md                      # Ejemplos de uso
│   └── PHASES.md                     # Explicaciones detalladas de fases
├── examples/
│   └── example-implementation.md    # Ejemplos del mundo real
├── README.md                         # Este archivo (Inglés)
├── README.es.md                      # Versión en español
├── LICENSE                           # Licencia MIT
└── CONTRIBUTING.md                   # Guía de contribución
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

FASE 3: Micro-tareas
→ Tarea 1: Función calcular_iva (50 líneas)
  → 3.1: Verificar skills (ninguna aplicable)
  → 3.2: Implementar función
  → 3.3: Auto-revisión ✓
  → 3.4: Generar tests (happy path, error, edge cases)
  → 3.5: Ejecutar tests → 5 passed
  → 3.6: Cobertura 100% ✓

→ Tarea 2: Función calcular_irpf (50 líneas)
  → [mismo ciclo]

FASE 4: Validación Integral
→ Seguridad: ✓ Validación de inputs
→ Tests: 10 passed, 0 failed, cobertura 100%
→ Calidad: ✓ Type hints completos
→ Rendimiento: ✓ Sin problemas
→ Arquitectura: ✓ Sin acoplamiento

FASE 5: Refinamiento
→ No necesario (ya ≥99%)

FASE 6: Entrega
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
- Diseñado para desarrollo asistido por IA en Cursor

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
