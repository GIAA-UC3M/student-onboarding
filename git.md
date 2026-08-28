# Git — Guía básica

Git registra la historia de cambios de tu código. Cada `commit` guarda una foto del estado de tu proyecto.

---

## Instalación

### Windows

Descarga e instala [Git for Windows](https://git-scm.com/download/win). Incluye **Git Bash**, una terminal donde ejecutar todos los comandos de esta guía.

### macOS

Abre Terminal y ejecuta:

```bash
git --version
```

Si no está instalado, macOS te ofrecerá instalarlo. Alternativamente, con [Homebrew](https://brew.sh):

```bash
brew install git
```

### Linux

```bash
# Ubuntu / Debian
sudo apt install git

# Fedora / RHEL
sudo dnf install git
```

---

## Configuración inicial (una sola vez)

Identifícate con el mismo nombre y correo que usas en GitHub:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

---

## Clonar tu repositorio

Descarga el repositorio a tu máquina (necesitas tener [autenticación configurada](github.md) primero):

```bash
git clone https://github.com/GIAA/{student-id}
cd {student-id}
```

---

## Comandos del día a día

### Ver el estado de tus cambios

```bash
git status
```

### Ver el historial de commits

```bash
git log --oneline
```

### Cambiar a la rama del ejercicio

El sistema crea la rama del ejercicio por ti. El nombre exacto aparece en la PR que recibes:

```bash
git checkout ex/{subject-id}/{course}/ex01
```

Si acabas de clonar el repo y la rama ya existe en GitHub, usa:

```bash
git checkout --track origin/ex/{subject-id}/{course}/ex01
```

### Guardar cambios (commit)

```bash
git add .                          # prepara todos los ficheros modificados
git commit -m "descripción breve"  # guarda la foto con un mensaje
```

### Subir tus commits a GitHub

```bash
git push
```

### Descargar los últimos cambios

```bash
git pull
```

---

## Resolución de conflictos

Un conflicto ocurre cuando dos personas modifican la misma línea del mismo fichero. En este flujo de trabajo es poco probable, ya que trabajas en tu propia rama privada.

Si ocurre: [Resolución de conflictos — Pro Git](https://git-scm.com/book/es/v2/Ramificaciones-en-Git-Procedimientos-b%C3%A1sicos-para-ramificarse-y-fusionarse).

---

## Más recursos

- [Pro Git (libro oficial, en español)](https://git-scm.com/book/es/v2) — referencia completa y gratuita.
- [git — la guía sencilla](https://rogerdudler.github.io/git-guide/index.es.html) — resumen visual de los comandos más usados.
- [Referencia de comandos git](https://git-scm.com/docs) — documentación oficial.
