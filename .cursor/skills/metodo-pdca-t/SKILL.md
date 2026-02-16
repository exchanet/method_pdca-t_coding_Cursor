# Método PDCA-T Mejorado con Validación ≥99%

Método de trabajo sistemático para desarrollo de software con garantía de calidad ≥99% mediante ciclo PDCA-T mejorado.

## Cuándo usar esta skill

Esta skill debe activarse automáticamente para TODAS las tareas de desarrollo, sin excepción. Define el flujo de trabajo estándar del agente.

## El método completo

### Ciclo PDCA-T Mejorado

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

## Fases detalladas

### FASE 1: PLANIFICACIÓN INICIAL

**Objetivo:** Comprender claramente qué hay que hacer.

**Acciones:**
- Analiza el objetivo general
- Identifica el alcance exacto
- Pregunta si algo no está claro
- **Output:** Comprensión clara de lo que hay que hacer

### FASE 2: ANÁLISIS DE REQUISITOS

**Objetivo:** Identificar todos los requisitos y riesgos.

**Acciones:**
- Identifica requisitos funcionales
- Identifica requisitos no funcionales (seguridad, rendimiento, escalabilidad)
- Identifica riesgos potenciales
- **Output:** Lista de requisitos y riesgos

### FASE 3: DIVISIÓN EN MICRO-TAREAS

**Objetivo:** Dividir el trabajo en tareas manejables de máximo 50 líneas cada una.

**Acciones:**
- Divide el trabajo en micro-tareas
- Cada micro-tarea debe ser independiente y testeable
- Ejecuta el sub-ciclo para cada micro-tarea:

#### 3.1 Verificar skills disponibles
- Revisa si hay skills aplicables en `.cursor/skills/`
- Si existe una skill relevante, úsala automáticamente
- Si no, ejecuta con mejores prácticas generales

#### 3.2 Ejecutar la tarea
- Type hints completos (Python 3.12+ o TypeScript)
- Buenas prácticas de seguridad
- Cero hardcoding (todo configurable)
- Manejo de excepciones específicas
- Logging estructurado

#### 3.3 Auto-revisión inmediata
- Verifica type hints
- Revisa vulnerabilidades de seguridad
- Detecta código duplicado
- Evalúa legibilidad y mantenibilidad
- Confirma mejores prácticas del lenguaje

#### 3.4 Generar tests COMPLETOS

**Mínimo obligatorio:**
- [ ] Test de caso feliz (happy path)
- [ ] Test de caso de error (validación, excepciones)
- [ ] Test de caso límite (edge case)
- [ ] Test de valores frontera
- [ ] Test de entrada inválida
- [ ] Test de seguridad (inyección, permisos)
- [ ] Test de rendimiento si aplica

#### 3.5 EJECUTAR tests y mostrar resultado

**OBLIGATORIO:** Ejecuta los tests y muestra:
- Número total de tests ejecutados
- Cuántos pasaron
- Cuántos fallaron
- Cuántos están pendientes

#### 3.6 Validar cobertura y calidad

- ¿Los tests pasan al 100%?
- ¿Cobertura estimada ≥99%?
- ¿Hay algún caso no cubierto?

Si cobertura < 99% o hay tests fallando:
1. Identifica qué falta cubrir
2. Mejora el código o los tests
3. Repite desde 3.4 hasta alcanzar ≥99%

### FASE 4: VALIDACIÓN INTEGRAL CON MÉTRICAS

Al completar todas las micro-tareas, genera un reporte con:

1. **Validación de Seguridad**
   - Sin vulnerabilidades críticas
   - Validación de inputs en todos los endpoints
   - Sanitización de outputs
   - Sin hardcoding de secrets
   - Permisos RBAC correctamente aplicados

2. **Validación de Tests**
   - Total de tests ejecutados
   - Tests pasados (100%)
   - Tests fallados (0)
   - Cobertura estimada (≥99%)
   - Casos cubiertos: Happy path, error, edge cases, seguridad

3. **Validación de Calidad de Código**
   - Type hints: 100% cobertura
   - Complejidad ciclomática < 10 por función
   - Sin código duplicado
   - Nombres de variables semánticos
   - Funciones con una sola responsabilidad

4. **Validación de Rendimiento**
   - Sin N+1 queries
   - Índices adecuados en consultas frecuentes
   - Paginación en listados
   - Timeouts configurados

5. **Validación de Arquitectura**
   - Sin importaciones circulares
   - Capas respetadas
   - Módulos sin acoplamiento indebido

### FASE 5: REFINAMIENTO HASTA ≥99%

Si alguna métrica no alcanza el 99%:

1. Identifica el problema
2. Evalúa el impacto (alto/medio/bajo)
3. Define acción correctiva
4. Implementa la corrección
5. Re-ejecuta tests
6. Verifica que cobertura ≥99%

### FASE 6: ENTREGA CON REPORTE DE TESTS

Genera un reporte final con:

- **Resumen de la implementación** (2-3 líneas)
- **Reporte de tests:**
  - Total tests: XX
  - Pasados: XX (100%)
  - Fallados: 0
  - Cobertura: ≥99%
- **Ejecución detallada** (output completo de pytest)
- **Decisiones clave** (con justificaciones)
- **Próximos pasos sugeridos**

## Reglas absolutas

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

## Ejemplos de uso

### Ejemplo 1: Implementar nueva función

```
FASE 1: Planificación
→ Objetivo: Crear función de cálculo de impuestos

FASE 2: Análisis de Requisitos
→ Requisitos funcionales: Calcular IVA, IRPF
→ Requisitos no funcionales: Precisión decimal, rendimiento
→ Riesgos: Errores de redondeo, valores negativos

FASE 3: Micro-tareas
→ Tarea 1: Función calcular_iva (50 líneas)
  → 3.1: Verificar skills (no aplica)
  → 3.2: Implementar función
  → 3.3: Auto-revisión
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

## Notas importantes

- Este método debe aplicarse SIEMPRE, sin excepción
- Si un proyecto no tiene pytest configurado, proponer alternativas manteniendo el mismo rigor
- La cobertura del 99% es un objetivo; si es imposible alcanzarlo, documentar por qué y proponer alternativas
- La transparencia es clave: siempre mostrar resultados de tests y explicar decisiones
