# Control de versiones

## Source Code Management (SCM)
La gestión de código fuente (SCM) es la práctica de rastrear modificaciones al código fuente. Mantener un historial de ejecución de los cambios realizados en una base de código ayuda a los programadores, desarrolladores y probadores a garantizar que siempre estén trabajando con código preciso y actualizado y ayuda a resolver conflictos al fusionar código de múltiples fuentes.
La gestión del código fuente resuelve problemas mediante:
- Seguimiento de los cambios de cada desarrollador.
- Destacando los conflictos.
- Evitar la sobreescritura de código.
Los desarrolladores son alertados de cualquier conflicto para que puedan abordarlos antes de que se fusionen en el código fuente y potencialmente comprometan la aplicación.
### Componentes
El SCM involucra componentes y conceptos clave que en conjunto forman un sistema cohesivo para gestionar los cambios en nuestro codebase. Estos incluyen repositories, branching, merging y commits.
- Repositories: Un repository (repo) almacena todo el código del proyecto, incluyendo su historial, cambios y archivos de configuración. Los repositories de SCM pueden estar alojados localmente o en servidores remotos accesibles para todo el equipo. Dependiendo del proyecto, pueden ser públicos o privados. 
- Branching: Permite crear líneas de desarrollo separadas dentro del mismo codebase. Una branch funciona como una copia aislada del proyecto, lo que permite realizar cambios sin impactar la versión principal del código. Al usar branches, los miembros individuales del equipo pueden trabajar en diferentes aspectos del proyecto de forma concurrente.
- Merging: Es el proceso mediante el cual tomamos los cambios realizados en una feature branch o bugfix branch y los combinamos con la main branch. En muchos casos, el merge ocurre de forma automática sin conflictos. Sin embargo, cuando múltiples cambios afectan la misma parte del código, puede ser necesaria una corrección manual para resolver los conflictos.
- Commits: registra los cambios realizados al codebase. Cada vez que se modifica el código, se crea un commit que incluye una breve descripción de las actualizaciones. En conjunto, estos commits construyen la base del historial del proyecto.
Varias herramientas manejan al gestión de código fuente (SCM), siendo GIT, Subversion, y Mercurial las más populares.

## GIT
La diferencia principal entre Git y cualquier otro VCS (Subversion y compañía incluidos) es la forma en que Git concibe sus datos. Conceptualmente, la mayoría de los demás sistemas almacenan la información como una lista de cambios basados en archivos. En su lugar, Git concibe sus datos más como una serie de snapshots de un mini sistema de archivos. Con Git, cada vez que hacés un commit o guardás el estado de tu proyecto, Git básicamente toma una foto de cómo se ven todos tus archivos en ese momento y almacena una referencia a ese snapshot. Para ser eficiente, si los archivos no cambiaron, Git no los vuelve a almacenar, solo guarda un enlace al archivo idéntico anterior que ya tiene almacenado. Git concibe sus datos más como un flujo de snapshots. La mayoría de las operaciones en Git solo necesitan archivos y recursos locales para funcionar.
### Working tree, staging area y Git directory
Git tiene tres estados principales en los que pueden residir tus archivos: modified, staged y committed:
- Modified significa que cambiaste el archivo pero todavía no lo commiteaste a tu base de datos.
- Staged significa que marcaste un archivo modificado en su versión actual para que vaya en tu próximo snapshot de commit.
- Committed significa que los datos están almacenados de forma segura en tu base de datos local.
El working tree es un checkout único de una versión del proyecto. Estos archivos se extraen de la base de datos comprimida en el Git directory y se colocan en disco para que los uses o modifiques.
El staging area es un archivo, generalmente contenido en tu Git directory, que almacena información sobre qué va a ir en tu próximo commit. 
El Git directory es donde Git almacena los metadatos y la base de datos de objetos para tu proyecto. Esta es la parte más importante de Git, y es lo que se copia cuando hacés un clone de un repository desde otra computadora.
### Flujo de trabajo
El flujo de trabajo básico de Git es algo así:
- Modificás archivos en tu working tree.
- Seleccionás y stageás solo aquellos cambios que querés que sean parte de tu próximo commit, lo que añade solamente esos cambios al staging area.
- Hacés un commit, que toma los archivos tal como están en el staging area y almacena ese snapshot de forma permanente en tu Git directory.
Si una versión particular de un archivo está en el Git directory, se considera committed. Si fue modificado y fue agregado al staging area, está staged. Y si fue cambiado desde que se hizo el checkout pero no fue stageado, está modified.
### Comandos más usados

| Comando | Qué hace |
|---|---|
| `git config` | Lee y escribe opciones de configuración (usuario, email, alias). |
| `git init` | Inicializa un repositorio nuevo en el directorio actual. |
| `git clone <url>` | Descarga una copia completa de un repositorio remoto. |
| `git add <archivo>` | Mueve archivos al área de ensayo. |
| `git status` | Muestra el estado del directorio de trabajo y el área de ensayo. |
| `git diff` | Muestra cambios no preparados. |
| `git diff --staged` | Muestra cambios en el área de ensayo. |
| `git commit -m "msg"` | Crea una confirmación con los cambios preparados. |
| `git restore <archivo>` | Descarta cambios del directorio de trabajo. |
| `git log` | Muestra el historial de confirmaciones. |
| `git branch` | Lista ramas. |
| `git branch <nombre>` | Crea una rama nueva. |
| `git switch <rama>` | Cambia a otra rama. |
| `git merge <rama>` | Fusiona otra rama en la actual. |
| `git remote -v` | Lista los remotos configurados. |
| `git fetch` | Descarga cambios remotos sin fusionar. |
| `git pull` | Descarga cambios remotos y los fusiona. |
| `git push` | Envía tus confirmaciones al remoto. |
| `git stash` | Guarda cambios sin confirmar. |
| `git reset <archivo>` | Saca un archivo del área de ensayo. |
| `git rebase <rama>` | Re-aplica tus confirmaciones sobre otra rama. |
| `git cherry-pick <conf>` | Aplica una confirmación específica. |
| `git blame <archivo>` | Muestra quién modificó cada línea. |