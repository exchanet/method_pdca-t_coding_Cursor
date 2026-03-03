# Contributing to Method PDCA-T / Contribuir al Metodo PDCA-T

---

## ENGLISH

Thank you for your interest in improving Method PDCA-T.

### What we appreciate most
- New agent adapters (for agents not yet covered)
- Stack-specific examples (Node.js, Go, TypeScript, Java, etc.)
- Real project demos showing PDCA-T applied end-to-end
- Improvements to templates (delivery report, ADR, debt register)
- Translations or corrections to the bilingual documentation

### How to contribute

1. Fork the repository
2. Create a feature branch: git checkout -b feature/your-contribution
3. Make your changes following the guidelines below
4. Commit with a descriptive message:
   - feat: add Gemini adapter
   - docs: improve Phase 3 examples
   - fix: correct Windsurf adapter path
5. Push and open a Pull Request with what you changed and why

### Guidelines

New adapters:
- Follow the structure of an existing adapter (e.g. adapters/cursor.md)
- Include all 8 phases in condensed form
- Note the specific installation path for that agent
- Test that the adapter actually works before submitting

New examples:
- Place in examples/[name]/
- Include a README.md explaining the scenario
- Show real test output (not hypothetical)
- Include the full delivery report

Documentation changes:
- Keep EN and ES versions in sync
- Code examples must be syntactically correct

---

## ESPANOL

Gracias por tu interes en mejorar el Metodo PDCA-T.

### Que valoramos mas
- Nuevos adapters para agentes no cubiertos aun
- Ejemplos especificos de stack (Node.js, Go, TypeScript, Java, etc.)
- Demos de proyectos reales con PDCA-T aplicado de principio a fin
- Mejoras a los templates
- Traducciones o correcciones a la documentacion bilingue

### Como contribuir

1. Fork del repositorio
2. Crear una rama: git checkout -b feature/tu-contribucion
3. Hacer los cambios siguiendo las guias de abajo
4. Commit: git commit -m "feat: agregar adapter para Gemini"
5. Push y abrir un Pull Request

### Guias

Nuevos adapters:
- Seguir la estructura de un adapter existente
- Incluir las 8 fases en forma condensada
- Indicar la ruta de instalacion especifica para ese agente
- Probar que el adapter funciona antes de enviarlo
