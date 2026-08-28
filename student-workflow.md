# Flujo de trabajo — Entregar ejercicios

---

## 1. Recibes un nuevo ejercicio

Cuando el profesor publica un ejercicio, recibirás una **notificación de GitHub** (correo o en [github.com/notifications](https://github.com/notifications)) con una **issue** asignada a ti.

Lo que el sistema crea automáticamente depende del modo del ejercicio:

| Modo | Qué crea el sistema | Qué debes hacer tú |
|---|---|---|
| **`full`** (habitual) | Issue + rama + draft PR con el enunciado | Trabajar en la rama; convertir la PR a Ready for Review |
| **`manual`** | Solo la issue con el enunciado | Crear la rama y la PR manualmente (ver abajo) |

### Modo manual: crear la rama y la PR tú mismo

Si el ejercicio es de modo `manual`, la issue te lo indicará. Debes:

```bash
# 1. Actualiza el repo
git pull

# 2. Crea la rama con el nombre exacto que indica la issue
git checkout -b ex/{subject-id}/{course}/exNN

# 3. Haz tu primer commit y sube la rama
git add .
git commit -m "inicio ejercicio exNN"
git push --set-upstream origin ex/{subject-id}/{course}/exNN
```

Luego abre una PR en GitHub desde esa rama hacia `main` y déjala como **draft** mientras trabajas.

> **El nombre de rama es obligatorio**. Si usas otro nombre, el sistema no detectará tu entrega al cerrar el plazo.

---

## 2. Prepara tu entorno local

Asegúrate de tener el repositorio actualizado:

```bash
cd {student-id}
git pull
```

Cambia a la rama del ejercicio. El nombre exacto aparece en la descripción de la draft PR:

```bash
git checkout ex/{subject-id}/{course}/exNN
```

Si acabas de clonar el repo y la rama no aparece en local:

```bash
git checkout --track origin/ex/{subject-id}/{course}/exNN
```

---

## 3. Trabaja y guarda tu progreso

Haz tus cambios en local. Guárdalos con commits y súbelos:

```bash
git add .
git commit -m "descripción de lo que has hecho"
git push
```

Puedes hacer tantos commits y pushes como necesites. Cada push actualiza la draft PR en GitHub.

> Los mensajes de commit son libres — no hay un formato obligatorio. Usa descripciones breves que expliquen qué cambiaste.

---

## 4. Entrega

Cuando tu trabajo esté listo, convierte la draft PR a **"Ready for Review"**:

1. Ve a tu repositorio en GitHub.
2. Abre la pestaña **Pull requests**.
3. Abre la PR del ejercicio.
4. Haz clic en **"Ready for review"**.

Eso es todo.

> **Importante**: no cambies el nombre de la rama ni cierres la PR manualmente. El sistema detecta tu entrega a través del nombre de rama `ex/{subject-id}/{course}/exNN`.

---

## 5. Confirma que se registró bien

Tu entrega está registrada cuando la PR aparece como **Open (no draft)** en tu repositorio. Verás la label `submission`.

Si conviertes la PR después de la fecha límite, el sistema añade la label `late-submission`. Tu profesor decidirá si afecta a la nota.

---

## 6. La nota

Cuando el profesor corrija y califique, recibirás una notificación y una issue `correction-review` en tu repo con la nota y el feedback.

---

## Preguntas frecuentes

**¿Puedo entregar tarde?**
Sí. La PR tendrá la label `late-submission` y tu profesor decide si penaliza.

**¿Qué pasa si cambio el nombre de la rama?**
El sistema no detectará tu entrega al cerrar el plazo y registrará `submission-pr-state: missing`. Usa siempre la rama que crea el sistema.

**¿Cómo sé el nombre exacto de la rama?**
Aparece en la descripción de la draft PR que recibes con el ejercicio.

**¿Puedo hacer commits después de convertir la PR a "Ready for Review"?**
Sí. Los commits adicionales siguen actualizando la PR. El sistema toma el estado de la rama en el momento de cierre del plazo.

**No veo la draft PR después de recibir la notificación.**
Espera unos minutos — el workflow puede tardar en ejecutarse. Si pasados 5 minutos sigue sin aparecer, avisa a tu profesor.

**¿Dónde veo mi nota?**
En la pestaña **Issues** de tu repositorio. Busca la issue `correction-review` con el nombre del ejercicio.
