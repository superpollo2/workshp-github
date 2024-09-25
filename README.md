# workshop-github
¿Sabías que tu perfil de GitHub puede ser mucho más que una simple lista de repositorios? es tu portafolio profesional, en este workshop, aprenderás a transformar tu perfil de GitHub en una verdadera carta de presentación. Te mostraremos cómo personalizar tu perfil para visualizar tus habilidades, proyectos y logros.

## Crea un nuevo repo secreto
1. Crear un nuevo repositorio (parte superior derecha dentro la navegación)
<img src="https://github.com/user-attachments/assets/70a74d1d-7913-4c6c-a80e-f34b4173345f" alt="new repo" width="200">

  
2. En el nombre de repositorio colocar el mismo nombre de usuario que tenemos
Al colocarlo te aparece el mensaje de que el owner/owner es un repositorio especial
que se puede usar para agregar un README a tu perfil de GitHub
***Es importante que selecciones las opciones de:
- Public
- Add a README file***
    
![image](https://github.com/user-attachments/assets/f5ee47ac-0359-48cf-a7cc-38df5dd7a415)

1. Vuelve al inicio de tu perfil para ver el resultado
![image](https://github.com/user-attachments/assets/b0355506-77c3-4af9-9729-f324648f79f8)

## Usemos Git Actions para construir metricas

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

## Otros recursos

### Iconos tecnologías o saberes
https://github.com/tandpfun/skill-icons 
```
[![My Skills](https://skillicons.dev/icons?i=java,kotlin,nodejs,figma&theme=light)](https://skillicons.dev)
```

[![My Skills](https://skillicons.dev/icons?i=java,kotlin,nodejs,figma&theme=light)](https://skillicons.dev)

```
[![My Skills](https://skillicons.dev/icons?i=js,html,css,wasm)](https://skillicons.dev)
```
[![My Skills](https://skillicons.dev/icons?i=js,html,css,wasm)](https://skillicons.dev)

### Badges
https://github.com/VishwaGauravIn/pretty-readme-badges
https://github.com/Naereen/badges
https://github.com/alexandresanlim/Badges4-README.md-Profile

```
![Pug](https://img.shields.io/badge/Pug-FFF?logo=pug&logoColor=A86454)
```
![Pug](https://img.shields.io/badge/Pug-FFF?logo=pug&logoColor=A86454)
![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?logo=Canva&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?logo=jupyter&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?logo=git&logoColor=white)
