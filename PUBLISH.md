# Instrucciones para Publicar en GitHub desde Consola

Guía paso a paso para publicar el repositorio en GitHub usando comandos de terminal.

**Author:** Francisco J Bernades  
**GitHub:** [@exchanet](https://github.com/exchanet)

---

## 📋 Prerrequisitos

Antes de comenzar, asegúrate de tener:

1. **Git instalado** en tu sistema
2. **Cuenta de GitHub** creada
3. **Autenticación configurada** (SSH key o Personal Access Token)

### Verificar Git instalado

```bash
git --version
```

Si no está instalado:
- **Windows:** Descarga desde [git-scm.com](https://git-scm.com/download/win)
- **Mac:** `brew install git` o descarga desde [git-scm.com](https://git-scm.com/download/mac)
- **Linux:** `sudo apt-get install git` (Ubuntu/Debian) o `sudo yum install git` (CentOS/RHEL)

### Verificar autenticación GitHub

```bash
# Probar conexión SSH (si usas SSH)
ssh -T git@github.com

# O verificar configuración HTTPS
git config --global user.name
git config --global user.email
```

Si no está configurado:

```bash
# Configurar nombre y email
git config --global user.name "Francisco J Bernades"
git config --global user.email "tu-email@ejemplo.com"
```

---

## 🚀 Pasos para Publicar

### Paso 1: Navegar al Directorio del Repositorio

```bash
cd method_pdca-t_coding_Cursor
```

### Paso 2: Inicializar Repositorio Git (si no está inicializado)

```bash
# Verificar si ya es un repositorio git
git status

# Si no es un repositorio git, inicializar
git init
```

### Paso 3: Crear Repositorio en GitHub (desde consola)

#### Opción A: Usar GitHub CLI (gh) - Recomendado

Si tienes GitHub CLI instalado:

```bash
# Verificar si gh está instalado
gh --version

# Si no está instalado, instálalo:
# Windows: winget install GitHub.cli
# Mac: brew install gh
# Linux: Ver instrucciones en https://cli.github.com/

# Autenticarse con GitHub CLI
gh auth login

# Crear repositorio y hacer push en un solo comando
gh repo create method_pdca-t_coding_Cursor --public --source=. --remote=origin --push
```

#### Opción B: Crear manualmente desde GitHub.com

Si prefieres crear el repositorio manualmente:

1. Ve a [github.com/new](https://github.com/new)
2. Nombre del repositorio: `method_pdca-t_coding_Cursor`
3. Descripción: `A systematic, quality-assured coding methodology for Cursor AI that guarantees ≥99% test coverage and zero-production-bugs`
4. Visibilidad: **Public**
5. **NO marques** "Add a README file" (ya tenemos uno)
6. **NO marques** "Add .gitignore" (ya tenemos uno)
7. **NO marques** "Choose a license" (ya tenemos uno)
8. Click en **"Create repository"**

Luego continúa con los siguientes pasos.

### Paso 4: Agregar Todos los Archivos

```bash
# Ver qué archivos se van a agregar
git status

# Agregar todos los archivos
git add .

# Verificar qué se agregó
git status
```

### Paso 5: Crear Commit Inicial

```bash
git commit -m "Initial commit: PDCA-T Enhanced Coding Method for Cursor AI

- Complete PDCA-T methodology documentation
- Cursor rule with auto-activation
- Reusable skill for other projects
- Comprehensive installation and usage guides
- Real-world implementation examples"
```

### Paso 6: Agregar Remote (si no usaste GitHub CLI)

```bash
# Agregar el repositorio remoto
git remote add origin https://github.com/exchanet/method_pdca-t_coding_Cursor.git

# Verificar que se agregó correctamente
git remote -v
```

**Nota:** Si prefieres usar SSH en lugar de HTTPS:

```bash
git remote add origin git@github.com:exchanet/method_pdca-t_coding_Cursor.git
```

### Paso 7: Renombrar Rama Principal (si es necesario)

```bash
# Verificar nombre de rama actual
git branch

# Renombrar a 'main' si está en 'master' u otro nombre
git branch -M main
```

### Paso 8: Hacer Push al Repositorio

```bash
# Push inicial a GitHub
git push -u origin main
```

Si GitHub te pide autenticación:

**Para HTTPS:**
- Usuario: `exchanet`
- Contraseña: Usa un **Personal Access Token** (no tu contraseña de GitHub)
  - Crear token: [github.com/settings/tokens](https://github.com/settings/tokens)
  - Permisos necesarios: `repo` (acceso completo a repositorios)

**Para SSH:**
- Asegúrate de tener tu SSH key agregada a GitHub
- Verificar: `ssh -T git@github.com`

---

## ✅ Verificación

Después del push, verifica que todo se subió correctamente:

```bash
# Verificar estado
git status

# Ver commits
git log --oneline

# Verificar remote
git remote -v
```

Luego ve a tu repositorio en GitHub:
```
https://github.com/exchanet/method_pdca-t_coding_Cursor
```

Deberías ver todos los archivos y el README.md renderizado.

---

## 🔄 Comandos Completos (Copy-Paste)

Si prefieres ejecutar todo de una vez (después de crear el repo en GitHub.com):

```bash
# Navegar al directorio
cd method_pdca-t_coding_Cursor

# Inicializar git (si no está inicializado)
git init

# Agregar todos los archivos
git add .

# Crear commit
git commit -m "Initial commit: PDCA-T Enhanced Coding Method for Cursor AI"

# Agregar remote
git remote add origin https://github.com/exchanet/method_pdca-t_coding_Cursor.git

# Renombrar rama a main
git branch -M main

# Push inicial
git push -u origin main
```

---

## 🐛 Solución de Problemas

### Error: "remote origin already exists"

```bash
# Ver el remote actual
git remote -v

# Eliminar el remote existente
git remote remove origin

# Agregar el correcto
git remote add origin https://github.com/exchanet/method_pdca-t_coding_Cursor.git
```

### Error: "Authentication failed"

**Solución 1: Usar Personal Access Token**
1. Ve a [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Selecciona permisos: `repo`
4. Genera el token y cópialo
5. Úsalo como contraseña cuando Git te la pida

**Solución 2: Configurar SSH**
```bash
# Generar SSH key (si no tienes una)
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"

# Copiar clave pública
cat ~/.ssh/id_ed25519.pub

# Agregar a GitHub: Settings → SSH and GPG keys → New SSH key
# Luego cambiar remote a SSH:
git remote set-url origin git@github.com:exchanet/method_pdca-t_coding_Cursor.git
```

### Error: "failed to push some refs"

```bash
# Si el repositorio en GitHub tiene contenido (README, etc.)
# Primero hacer pull y merge
git pull origin main --allow-unrelated-histories

# Resolver conflictos si los hay, luego:
git push -u origin main
```

### Error: "branch 'main' does not exist"

```bash
# Crear la rama main
git checkout -b main

# O renombrar la rama actual
git branch -M main

# Luego hacer push
git push -u origin main
```

---

## 📝 Actualizaciones Futuras

Para hacer cambios y actualizar el repositorio:

```bash
# Ver cambios
git status

# Agregar archivos modificados
git add .

# O agregar archivos específicos
git add archivo1.md archivo2.md

# Crear commit con mensaje descriptivo
git commit -m "Descripción de los cambios realizados"

# Hacer push
git push origin main
```

---

## 🎯 Configuración Adicional Recomendada

### Agregar Descripción y Topics desde Consola

```bash
# Usando GitHub CLI
gh repo edit exchanet/method_pdca-t_coding_Cursor \
  --description "A systematic, quality-assured coding methodology for Cursor AI" \
  --add-topic "cursor-ai" \
  --add-topic "coding-methodology" \
  --add-topic "pdca" \
  --add-topic "test-driven-development" \
  --add-topic "quality-assurance"
```

### Crear Release Inicial

```bash
# Usando GitHub CLI
gh release create v1.0.0 \
  --title "v1.0.0 - Initial Release" \
  --notes "First public release of the PDCA-T Enhanced Coding Method for Cursor AI.

## Features
- Complete PDCA-T methodology documentation
- Cursor rule with auto-activation
- Reusable skill for other projects
- Comprehensive installation guide
- Real-world usage examples"
```

---

## 📞 Ayuda Adicional

Si encuentras problemas:

1. **Verificar estado de Git:**
   ```bash
   git status
   git log --oneline -5
   ```

2. **Ver configuración:**
   ```bash
   git config --list
   ```

3. **Ver ayuda de comandos:**
   ```bash
   git help <comando>
   # Ejemplo: git help push
   ```

4. **Documentación oficial:**
   - Git: [git-scm.com/doc](https://git-scm.com/doc)
   - GitHub: [docs.github.com](https://docs.github.com)

---

**¡Listo para publicar!** Ejecuta los comandos paso a paso y tu repositorio estará en GitHub. 🚀
