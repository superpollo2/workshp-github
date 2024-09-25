# workshp-github
¿Sabías que tu perfil de GitHub puede ser mucho más que una simple lista de repositorios? es tu portafolio profesional, en este workshop, aprenderás a transformar tu perfil de GitHub en una verdadera carta de presentación. Te mostraremos cómo personalizar tu perfil para visualizar tus habilidades, proyectos y logros.

## Usemos Git Actions para construir matricas

### Crear nuevo token
1. Ve a **Settings** (Configuración) desde tu perfil.
2. Selecciona **Developer settings** en la barra lateral.
3. Haz clic en **Personal access tokens** y luego en **Tokens (classic)**.
4. Haz clic en **Generate new token**.
5. Escribe una descripción, selecciona permisos para `repo`.
6. Haz clic en **Generate token**.
7. Copia el token y guárdalo en un lugar seguro.

### Crea una nueva Variable de actions en el repositorio

1. Ve a tu **repositorio** en GitHub.
2. Haz clic en **Settings** (Configuración) en la parte superior del repositorio.
3. En la barra lateral izquierda, selecciona **Secrets and variables** y luego **Actions**.
4. Haz clic en **New repository secret**.
5. En el campo **Name**, escribe `METRICS_TOKEN`.
6. En el campo **Value**, pega el token que creaste.
7. Haz clic en **Add secret** para guardar el secreto.

Explicación del cron

 ```Scss
└── * * * * * * 
    ├── minute (0-59)
    ├── hour (0-23)
    ├── day_of_month (1-31)
    ├── month (1-12)
    ├── mday_of_week (0-6)
    └── year (1970-2199)
 ```

Workflow base
 ```yaml
name: Half-year calendar

on:
  schedule:
    - cron: "0 0 * * *" 
  workflow_dispatch:
  push:
    branches:
      - main
      
jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      # Checkout the repository
      - name: Checkout repository
        uses: actions/checkout@v3
 ```

Para insertar las imagenes creadas usa, recuerda cambiar la etiqueta
y el nombre del svg
```
![Languages Classic](images/languages.classic.svg)
```
![Languages Classic](lenguages.classic.svg)

También puedes poder uno al lado del otro para optimizar espacio o como tu 
quieras que se vea

![Languages Classic](lenguages.classic.svg)
![Languages Classic](metrics.plugin.isocalendar.svg)
