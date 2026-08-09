# Resumen — ¿Cómo funciona GIT?

> Documento principal de la sección **02**. Aquí se vuelca la investigación sobre GIT como herramienta SCM.

## 🎯 Alcance

- ¿Qué es un SCM y para qué sirve?
- ¿Qué es GIT y por qué es tan usado?
- Arquitectura: las 4 áreas (working dir, staging, repo local, repo remoto).
- Flujo básico: `add` → `commit` → `push` → `pull`.
- Comandos esenciales.

## 🧩 Áreas de GIT (a completar)

> **Acción:** agregar un diagrama o descripción de las 4 áreas:
> 1. **Working directory** — donde están tus archivos editables.
> 2. **Staging area** (index) — zona intermedia donde preparás lo que va al próximo commit.
> 3. **Local repository** (`.git`) — base de datos local con tu historial.
> 4. **Remote repository** (origin) — copia del repo en el servidor (GitHub, GitLab, etc.).

## 🛠️ Comandos básicos (a completar)

| Comando | Qué hace |
|---|---|
| `git init` | Inicializa un repositorio local |
| `git clone <url>` | Clona un repositorio remoto |
| `git add <archivo>` | Pasa un archivo al staging area |
| `git commit -m "msg"` | Confirma los cambios en el repo local |
| `git push` | Sube los commits al remoto |
| `git pull` | Baja y mezcla cambios del remoto |
| `git status` | Muestra el estado actual del working dir |
| `git log` | Muestra el historial de commits |
| `git branch` | Lista / crea ramas |
| `git checkout <rama>` | Cambia de rama |

## 🔄 Flujo típico (a completar)

> **Acción:** describir el flujo de trabajo con GIT:
> 1. Modificar archivos en el **working directory**.
> 2. `git add .` → pasar al **staging**.
> 3. `git commit -m "..."` → confirmar en el **repo local**.
> 4. `git push origin main` → subir al **repo remoto**.

## 📎 Ver también

- [Volver al hub de la sección 02](README.md)
- [Volver al hub principal](../README.md)
- [Evidencia de los commits](evidencia/commit-1.md)
