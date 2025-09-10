# Apunte rápido de Git para programar (Windows/Linux/Mac)

Hecho para usar con GitHub y proyectos web. Español rioplatense.

---

## 1) Configuración inicial (una sola vez)

- Nombre y email (aparecen en tus commits):  
  ```bash
  git config --global user.name "Tu Nombre"
  git config --global user.email "tu@email.com"
  ```
- Rama por defecto en **main**:  
  ```bash
  git config --global init.defaultBranch main
  ```
- Crear upstream automático al primer push:  
  ```bash
  git config --global push.autoSetupRemote true
  ```
- Alias útil para ver el historial bonito:  
  ```bash
  git config --global alias.lg "log --oneline --graph --decorate --all"
  ```

---

## 2) Flujo básico: proyecto nuevo a GitHub

| Paso    | Comando                                                       | Descripción                                      |
|---------|---------------------------------------------------------------|--------------------------------------------------|
| Init    | `git init`                                                    | Inicializá el repo en la carpeta actual         |
| Agregar | `git add .`                                                   | Prepará todos los archivos para el commit       |
| Commit  | `git commit -m "Primer commit"`                               | Creá el primer snapshot                          |
| Rama    | `git branch -M main`                                          | Asegurá nombre de rama en `main`                |
| Remoto  | `git remote add origin https://github.com/usuario/repo.git`   | Conectá con tu repo en GitHub                   |
| Push    | `git push -u origin main`                                     | Subí y vinculá la rama (upstream)               |

---

## 3) Flujo básico: repo existente (clonar y trabajar)

| Paso       | Comando                                          | Descripción                              |
|------------|--------------------------------------------------|------------------------------------------|
| Clonar     | `git clone https://github.com/usuario/repo.git`  | Bajar el repositorio                     |
| Estado     | `git status`                                     | Ver cambios                              |
| Agregar    | `git add <archivo>` &nbsp; ó &nbsp; `git add .`  | Seleccionar cambios a commitear          |
| Commit     | `git commit -m "Mensaje claro"`                  | Guardar cambios en la historia           |
| Actualizar | `git pull --rebase origin main`                  | Traer cambios remotos sin merge extra    |
| Subir      | `git push`                                       | Publicar tus commits                     |

---

## 4) Ramas (branching)

| Acción            | Comando                                | Notas                                      |
|-------------------|----------------------------------------|--------------------------------------------|
| Crear y moverse   | `git switch -c feature/login`          | Nueva rama llamada `feature/login`         |
| Listar            | `git branch`                           | Ramas locales                              |
| Cambiar           | `git switch main`                      | Volver a `main`                            |
| Merge             | `git merge feature/login`              | Combinar cambios en la rama actual         |
| Rebase (altern.)  | `git rebase main`                      | Reaplica tus commits sobre `main`          |
| Borrar rama       | `git branch -d feature/login`          | Borrado local (`-D` para forzar)           |
| Borrar en remoto  | `git push origin --delete feature/login`| Elimina la rama remota                     |

---

## 5) Sincronización y revisión

- Traer referencias del remoto: `git fetch origin`  
- Traer y rebasar sobre `main` (recomendado): `git pull --rebase origin main`  
- Ver historial bonito: `git lg` (si definiste el alias)

---

## 6) Guardar cambios temporales y deshacer (con cuidado)

| Acción                     | Comando                           | Para qué sirve                          |
|----------------------------|-----------------------------------|-----------------------------------------|
| Guardar temporal (stash)   | `git stash`                       | Guarda cambios sin commitear            |
| Volver del stash           | `git stash pop`                   | Recupera lo último guardado             |
| Sacar de stage             | `git restore --staged archivo`    | Quita un archivo del área de preparación|
| Descartar cambios          | `git restore archivo`             | Revierte cambios no commiteados         |
| Volver un commit (peligroso)| `git reset --hard HEAD~1`        | Deshace el último commit y cambios      |

---

## 7) Tags y versiones

- Crear tag: `git tag v1.0.0` &nbsp;&nbsp;|&nbsp;&nbsp; Listar: `git tag`  
- Subir tags: `git push origin --tags`

---

## 8) Errores comunes y soluciones rápidas

| Mensaje                                            | Causa                                                | Solución                                                                 |
|----------------------------------------------------|------------------------------------------------------|--------------------------------------------------------------------------|
| `The current branch main has no upstream branch`   | La rama local no está vinculada al remoto           | `git push -u origin main`                                                |
| `Updates were rejected (fetch first)`              | El remoto tiene commits que vos no tenés            | `git pull --rebase origin main` (usar `--allow-unrelated-histories` si aplica) |
| `src refspec main does not match any`              | No hay commits en la rama                           | `git add . && git commit -m "Primer commit"`                             |
| Conflictos en rebase/merge                         | Cambios incompatibles en los mismos archivos        | Editar archivos → `git add` → `git rebase --continue`                    |
| Falla de autenticación en push                     | GitHub no acepta password de cuenta                 | Usar **Personal Access Token** como password                             |
| Pisar lo del remoto (sabés lo que hacés)           | Necesitás forzar el push                            | `git push --force-with-lease` (más seguro que `--force`)                 |

---

## 9) Workflow recomendado para proyectos web

1. Crear rama por feature: `git switch -c feature/algo`  
2. Commits chicos y claros (ej.: `feat: agrega login`)  
3. Antes de subir: `git pull --rebase origin main`  
4. Push y PR/MR (si trabajás con equipo)  
5. Merge a `main` y borrar la rama

> **Tip**: agregá un `.gitignore` (Node: `node_modules/`, `dist/`, `.env`, etc.).
