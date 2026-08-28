# AGENTS.md

## Propósito del repositorio

Este repositorio contiene material docente en español para la asignatura
Ecuaciones Diferenciales Ordinarias. Las fuentes principales están escritas en
LaTeX y los PDF versionados son el material que consultan los estudiantes.

## Criterios de trabajo

- Escribir en español rioplatense claro, formal y pedagógico.
- Preservar la voz del docente y la notación usada en cada documento.
- Priorizar la corrección matemática. No introducir resultados, hipótesis o
  ejemplos cuya validez no se haya comprobado.
- Mantener los cambios acotados al archivo o a la clase solicitada; no
  homogeneizar todo el repositorio sin un pedido explícito.
- Respetar los nombres de archivos y carpetas, incluidos espacios, acentos y
  mayúsculas.
- No modificar archivos de bibliografía, programa o trabajos prácticos salvo
  pedido explícito.

## Convenciones LaTeX

- Conservar el preámbulo, estilo, estructura y sangría del documento editado.
- Usar entornos matemáticos de LaTeX y evitar reemplazar fórmulas por texto
  plano.
- Mantener coherentes la variable independiente y la notación de derivadas:
  usar `\dot y` para tiempo cuando el documento así lo establezca y `dy/dx`
  cuando la variable independiente sea `x`.
- Verificar referencias, etiquetas, numeración, dominios, condiciones iniciales
  e hipótesis de los teoremas después de editar contenido matemático.
- No agregar paquetes salvo que sean necesarios y estén disponibles en la
  instalación de LaTeX del proyecto.

## Compilación y verificación

Después de modificar un archivo `.tex` compilable:

1. Compilar con `pdflatex` al menos dos veces para resolver referencias.
2. Generar los archivos auxiliares fuera del repositorio, preferentemente bajo
   `/tmp`, mediante `-output-directory`.
3. Tratar advertencias de referencias indefinidas, errores de LaTeX y fórmulas
   desbordadas como problemas que deben revisarse.
4. Informar qué archivo se compiló y si la compilación terminó correctamente.

Ejemplo:

```bash
mkdir -p /tmp/edo-build
pdflatex -interaction=nonstopmode -halt-on-error \
  -output-directory=/tmp/edo-build "Clase III/Clase_III_Teórico.tex"
pdflatex -interaction=nonstopmode -halt-on-error \
  -output-directory=/tmp/edo-build "Clase III/Clase_III_Teórico.tex"
```

No sobrescribir un PDF versionado con una compilación fallida. Actualizar el PDF
del repositorio únicamente cuando el usuario lo solicite o cuando el pedido
incluya explícitamente entregar la versión compilada.

## Archivos generados y Git

- No versionar archivos auxiliares (`.aux`, `.log`, `.out`, `.toc`, `.fls`,
  `.fdb_latexmk`, `.synctex.gz`).
- No eliminar cambios existentes del usuario ni usar operaciones destructivas
  de Git.
- Antes de finalizar, revisar `git diff` y distinguir los cambios propios de los
  que ya estaban presentes.

## Alcance pedagógico

- El material está en preparación y puede contener secciones incompletas.
- Las explicaciones deben distinguir entre intuición, cálculo formal y
  afirmaciones teóricas.
- En ejemplos resueltos, comprobar la solución sustituyéndola en la ecuación y,
  cuando corresponda, en la condición inicial.
- Evitar cambios meramente estilísticos que dificulten revisar una corrección de
  contenido.
