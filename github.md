# GitHub — Guía básica

GitHub es la plataforma donde viven tus repositorios. Necesitas autenticarte desde tu máquina para poder hacer `push` y `pull`.

---

## Autenticación

Elige una de las dos opciones:

### Opción A — SSH (recomendado)

Una clave SSH identifica tu máquina automáticamente, sin introducir contraseña en cada operación.

1. [Genera una clave SSH](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
2. [Añade la clave pública a tu cuenta de GitHub](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
3. Cuando clones, usa la URL SSH: `git clone git@github.com:GIAA-UC3M/{student-id}.git`

### Opción B — Token personal (más sencillo para empezar)

1. En GitHub: **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token**.
2. Selecciona el scope **`repo`** y genera el token.
3. Guarda el token — solo se muestra una vez.
4. Cuando git te pida contraseña al hacer `push`, introduce el token.

Para no tener que introducirlo cada vez, configura el gestor de credenciales:

```bash
# macOS
git config --global credential.helper osxkeychain

# Windows (incluido con Git for Windows)
git config --global credential.helper manager

# Linux (guarda en disco; solo para máquinas personales)
git config --global credential.helper store
```

Guía oficial: [Crear un token de acceso personal](https://docs.github.com/es/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).

---

## Pull Requests (PRs)

Una PR es una propuesta de cambio de una rama hacia otra. En esta plataforma:

- Cuando recibes un ejercicio, el sistema crea una **draft PR** en tu nombre.
- Haces commits en la rama asociada.
- Cuando terminas, conviertes la draft PR a **"Ready for Review"** — esa es tu entrega.
- No la cierres ni la mergees tú: el sistema la mergea automáticamente cuando el profesor te califica.

### Partes de una PR

| Parte | Qué contiene |
|---|---|
| Descripción | El enunciado del ejercicio (lo pone el sistema) |
| Commits | Tus cambios |
| Conversación | Comentarios de revisión del profesor |

---

## Issues

Las issues son notificaciones o tareas. En esta plataforma, cada ejercicio que recibes aparece como una **issue asignada** en tu repositorio, con el enunciado y la fecha límite.

Puedes ver todas las issues en tu repo → pestaña **Issues**.

---

## Notificaciones

GitHub te notifica por correo y en [github.com/notifications](https://github.com/notifications) cuando:

- Te asignan una issue (nuevo ejercicio).
- Alguien comenta en tu PR (feedback del profesor).
- Tu nota está disponible.

Configura tus preferencias en: **Settings → Notifications**.
