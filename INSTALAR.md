# Territorio América — paquete para otro equipo

Versión: 2026-10-30. Incluye las correcciones hasta «es mi alumno» y el flujo de selección y cortes desde material crudo.

El ZIP contiene la carpeta completa `edicion-territorio-america/`: instrucciones, paleta, fuentes Archivo/Fraunces, PDF de marca y diseño sonoro, referencias de Liquid Glass, capturas, presets y helpers de animación. No necesita las rutas de la Mac de Maka ni su disco externo. Los videos originales, los renders y la biblioteca musical pertenecen a cada proyecto y no forman parte de esta skill; sus muestras/análisis sí están incluidos.

## Para pasárselo a otro asistente

Puedes pasar al asistente la página pública https://github.com/MakaGonzalez/edicion-territorio-america y pedirle que siga esta guía. El ZIP completo está en https://github.com/MakaGonzalez/edicion-territorio-america/releases/download/2026-10-30/edicion-territorio-america.zip . Si su entorno no permite descargar enlaces, descarga el ZIP y adjúntalo al chat. Puedes pedirle:

> Descarga e instala la skill edicion-territorio-america del enlace de esta guía en este equipo. Lee primero INSTALAR.md y verifica MANIFEST.sha256.json. Conserva una copia de la versión anterior si existe. Usa la ruta de skills del entorno actual y confirma por lectura que SKILL.md, fuentes, referencias y presets se copiaron correctamente. No edites videos ni publiques nada durante la instalación.

El asistente necesita acceso a los archivos del equipo y un entorno que admita skills. Si solo puede leer adjuntos, podrá usar las instrucciones como referencia, pero no debe afirmar que la instaló en el computador.

La descarga pública está en https://github.com/MakaGonzalez/edicion-territorio-america/releases/tag/2026-10-30 y no requiere iniciar sesión. También puedes adjuntar el ZIP directamente al otro chat. El respaldo general de otras skills permanece privado.

## Instalación con el instalador incluido

1. Descomprime el ZIP completo en una carpeta temporal.
2. Desde esa carpeta, verifica el paquete con Python 3:

```sh
python3 install_skill.py --verify
```

3. Identifica la carpeta de skills que reconoce el entorno de destino y pasa esa ruta expresamente al instalador:

```sh
python3 install_skill.py --skills-dir "/ruta/real/de/skills"
```

La [documentación actual de Codex](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills) describe `~/.agents/skills` para skills personales y `.agents/skills` para un proyecto. Algunos entornos existentes usan `~/.codex/skills` o `CODEX_HOME/skills`; comprueba la configuración real antes de copiar.

El instalador incluido conserva por compatibilidad el destino predeterminado `CODEX_HOME/skills` o `~/.codex/skills` si se ejecuta sin argumentos. Para instalar en otro equipo, usa siempre `--skills-dir` con el destino que hayas verificado. No crees dos instalaciones de la misma skill para intentar que aparezca.

El instalador verifica las huellas de todos los archivos antes de copiar. Si la skill ya es idéntica, lo indica sin duplicarla. Si existe otra versión, la conserva en una carpeta `skill-backups` junto al directorio de skills. No instala dependencias, abre editores, modifica otras skills ni autentica servicios.

También puedes copiar manualmente **la carpeta completa** `edicion-territorio-america`, conservando su estructura, a la ubicación de skills correspondiente. No copiar únicamente SKILL.md. Verifica después las fuentes y referencias; la detección/activación corresponde al entorno donde la instales.

## Uso y dependencias

- Las instrucciones de estilo y los presets JSON se pueden consultar sin ejecutar Python.
- `scripts/motion_primitives.py` usa Python 3; sus funciones de máscara, texto y composición requieren **Pillow**. Los helpers fueron probados con Python 3.12 y Pillow. No son un editor completo ni sustituyen FFmpeg u otra herramienta si el trabajo exige renderizar video.
- Las fuentes están en `assets/fonts/`, con sus licencias OFL. El uso desde código puede cargar esos archivos directamente; si un editor necesita fuentes del sistema, instalarlas mediante el procedimiento de ese equipo.
- La skill funciona independientemente de Resolve. Si se pide editar allí, necesita el acceso y procedimiento técnico de ese editor. Si se pide trabajo interno, respetar esa vía.
- Música, efectos y clips se obtienen de las rutas/conectores autorizados para cada encargo. La skill no incluye credenciales ni audios de biblioteca.

Las reglas actuales conservan del PDF la paleta y las familias tipográficas; el montaje dinámico y las correcciones de Maka tienen prioridad. El glosario de marca no reescribe lo hablado: «es mi alumno» se transcribe literalmente.

## Confirmar que está instalada

Comprueba que la carpeta de destino contiene SKILL.md, las fuentes, referencias y presets, y que el entorno reconoce `edicion-territorio-america`. Si copiaste los archivos pero aún no aparece en el selector, informa de esa diferencia; en Codex se puede reiniciar la aplicación para refrescar la detección. No afirmar que quedó instalada en el computador si solo se extrajo en un espacio temporal de un chat remoto.
