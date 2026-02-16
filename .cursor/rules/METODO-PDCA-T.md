---
trigger: always_on
---

# MÉTODO DE TRABAJO PDCA-T MEJORADO CON VALIDACIÓN ≥99%

Este método debe aplicarse SIEMPRE, para TODAS las tareas, sin excepción. Es la forma de trabajar por defecto del agente.

## EL MÉTODO (Ciclo PDCA-T Mejorado con Validación ≥99%)

Siempre que recibas una tarea, debes ejecutar este ciclo:

```
FASE 1: PLANIFICACIÓN
│
▼
FASE 2: ANÁLISIS DE REQUISITOS
│
▼
FASE 3: DIVISIÓN EN MICRO-TAREAS
│
▼
┌─────────────────────────────────────────────────┐
│  POR CADA MICRO-TAREA:                          │
│  ┌─────────────────────────────────────────┐    │
│  │ 3.1 Verificar skills disponibles        │    │
│  │ 3.2 Ejecutar con skill aplicada         │    │
│  │ 3.3 Auto-revisión                        │    │
│  │ 3.4 Generar tests COMPLETOS              │    │
│  │ 3.5 EJECUTAR tests y mostrar resultado   │    │
│  │ 3.6 Si cobertura < 99% → revisar y mejorar│    │
│  └─────────────────────────────────────────┘    │
└─────────────────────────────────────────────────┘
│
▼
FASE 4: VALIDACIÓN INTEGRAL CON MÉTRICAS
│
▼
FASE 5: REFINAMIENTO HASTA ≥99%
│
▼
FASE 6: ENTREGA CON REPORTE DE TESTS
```

## FASE 1: PLANIFICACIÓN INICIAL

- Analiza el objetivo general
- Identifica el alcance exacto
- Pregúntame si algo no está claro
- **Output:** Comprensión clara de lo que hay que hacer

## FASE 2: ANÁLISIS DE REQUISITOS

- Identifica requisitos funcionales
- Identifica requisitos no funcionales (seguridad, rendimiento, escalabilidad)
- Identifica riesgos potenciales
- **Output:** Lista de requisitos y riesgos

## FASE 3: DIVISIÓN EN MICRO-TAREAS

Divide el trabajo en tareas de **MÁXIMO 50 LÍNEAS DE CÓDIGO** cada una:
- Tarea 1: [descripción]
- Tarea 2: [descripción]
- etc.

Para **CADA micro-tarea**, ejecuta este sub-ciclo:

### 3.1 Verificar skills disponibles

Antes de escribir código, pregúntate:
- ¿Hay una skill en mi repositorio que pueda usar para esta tarea?
- Si SÍ: aplícala automáticamente
- Si NO: ejecuta la tarea con las mejores prácticas generales

### 3.2 Ejecutar la tarea

Escribe el código siguiendo:
- Type hints completos (Python 3.12) o tipos TypeScript completos
- Buenas prácticas de seguridad
- Cero hardcoding (todo configurable)
- Manejo de excepciones específicas
- Logging estructurado

### 3.3 Auto-revisión inmediata

Revisa el código que acabas de escribir:
- ¿Cumple con type hints?
- ¿Hay vulnerabilidades de seguridad?
- ¿Hay código duplicado?
- ¿Es legible y mantenible?
- ¿Sigue las mejores prácticas del lenguaje?

### 3.4 Generar tests COMPLETOS

Escribe tests unitarios para esta tarea que cubran:

**MÍNIMO OBLIGATORIO:**
- [ ] Test de caso feliz (happy path)
- [ ] Test de caso de error (validación, excepciones)
- [ ] Test de caso límite (edge case)
- [ ] Test de valores frontera
- [ ] Test de entrada inválida
- [ ] Test de seguridad (inyección, permisos)
- [ ] Test de rendimiento si aplica

```python
# Ejemplo de estructura de tests
def test_funcionalidad_happy_path():
    """Prueba que la funcionalidad funciona con inputs válidos."""
    # Arrange
    # Act
    # Assert

def test_funcionalidad_error():
    """Prueba que lanza error correcto con inputs inválidos."""
    with pytest.raises(ExpectedError):
        # código que debe fallar

def test_funcionalidad_edge_case():
    """Prueba casos límite (valores mínimos, máximos, vacíos, etc)."""
    # Test específico
```

### 3.5 EJECUTAR tests y mostrar resultado

**OBLIGATORIO:** Ejecuta los tests y muestra el resultado:

```bash
# Ejecución de tests
pytest tests/test_modulo.py -v

# Resultado:
# tests/test_modulo.py ✓ test_happy_path
# tests/test_modulo.py ✓ test_error_case
# tests/test_modulo.py ✓ test_edge_case
# tests/test_modulo.py ✓ test_security
#
# 4 passed, 0 failed, 0 skipped
```

**DEBES MOSTRAR:**
- Número total de tests ejecutados
- Cuántos pasaron
- Cuántos fallaron
- Cuántos están pendientes

### 3.6 Validar cobertura y calidad

- ¿Los tests pasan al 100%?
- ¿Cobertura estimada ≥99%?
- ¿Hay algún caso no cubierto?

Si cobertura < 99% o hay tests fallando:

1. Identifica qué falta cubrir
2. Mejora el código o los tests
3. Repite desde 3.4 hasta alcanzar ≥99%

## FASE 4: VALIDACIÓN INTEGRAL CON MÉTRICAS (al completar todas las tareas)

```markdown
## 📊 REPORTE DE VALIDACIÓN INTEGRAL

### 1. VALIDACIÓN DE SEGURIDAD
- [ ] Sin vulnerabilidades críticas
- [ ] Validación de inputs en todos los endpoints
- [ ] Sanitización de outputs
- [ ] Sin hardcoding de secrets
- [ ] Permisos RBAC correctamente aplicados

### 2. VALIDACIÓN DE TESTS
- **Total de tests ejecutados:** [XX]
- **Tests pasados:** [XX] (100%)
- **Tests fallados:** [0]
- **Cobertura estimada:** [≥99%]
- **Casos cubiertos:** Happy path, error, edge cases, seguridad

### 3. VALIDACIÓN DE CALIDAD DE CÓDIGO
- [ ] Type hints: 100% cobertura
- [ ] Complejidad ciclomática < 10 por función
- [ ] Sin código duplicado
- [ ] Nombres de variables semánticos
- [ ] Funciones con una sola responsabilidad

### 4. VALIDACIÓN DE RENDIMIENTO
- [ ] Sin N+1 queries
- [ ] Índices adecuados en consultas frecuentes
- [ ] Paginación en listados
- [ ] Timeouts configurados

### 5. VALIDACIÓN DE ARQUITECTURA
- [ ] Sin importaciones circulares
- [ ] Capas respetadas
- [ ] Módulos sin acoplamiento indebido
```

## FASE 5: REFINAMIENTO HASTA ≥99%

Si alguna métrica no alcanza el 99%:

```markdown
## 🔄 CICLO DE REFINAMIENTO

**Problema identificado:** [descripción]
**Impacto:** [alto/medio/bajo]
**Acción correctiva:** [qué voy a hacer]
**Validación:** [cómo verificaré que está corregido]

**Ejecutando corrección...**
[Implementar cambios]

**Re-ejecutando tests...**
[Mostrar resultados]

**¿Cobertura ahora ≥99%?** [SÍ/NO]
```

## FASE 6: ENTREGA CON REPORTE DE TESTS

```markdown
## ✅ ENTREGA FINAL

### Resumen de la implementación
[2-3 líneas describiendo qué se implementó]

### Reporte de tests
- Total tests: XX
- Pasados: XX (100%)
- Fallados: 0
- Cobertura: ≥99%

### Ejecución detallada
```
pytest tests/ -v
[Pegar output completo de la ejecución]
```

### Decisiones clave
- [Decisión 1]: [justificación]
- [Decisión 2]: [justificación]

### Próximos pasos sugeridos
1. [Siguiente tarea recomendada]
2. [Puntos de atención]
```

## REGLAS ABSOLUTAS (NO NEGOCIABLES)

### 1. TESTS OBLIGATORIOS
- Toda función DEBE tener tests
- Los tests DEBEN ejecutarse y mostrarse
- La cobertura DEBE ser ≥99%

### 2. SEGURIDAD ANTE TODO
- Nunca expongas información sensible
- Siempre valida inputs
- Siempre sanitiza outputs

### 3. ZERO VULNERABILIDADES
- Sin inyección SQL
- Sin hardcoding de secrets
- Sin exposición de datos sensibles

### 4. ZERO BUGS EN PRODUCCIÓN
- Cada línea debe tener propósito
- Cada función debe tener tests
- Cada edge case debe considerarse
- Validación ≥99% antes de entregar

### 5. TRANSPARENCIA TOTAL
- Muestra siempre los resultados de tests
- Explica decisiones técnicas
- Pregunta cuando tengas dudas
- Reporta problemas encontrados

## MI REPOSITORIO DE SKILLS

En la carpeta `.cursor/skills/` pueden existir skills que debo usar cuando corresponda. Antes de cada tarea, debo revisar si alguna skill aplica.

## ACTIVACIÓN PERMANENTE

Este método debe aplicarse SIEMPRE, para TODAS las tareas, sin excepción. Es mi forma de trabajar por defecto.
