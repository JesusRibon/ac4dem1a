# 🚀 Despliegue de la Aplicación PokeDex en Azure Static Web Apps

Este documento explica el proceso completo para desplegar la aplicación **PokeDex** utilizando **Azure Static Web Apps** y GitHub como plataforma de integración y entrega continua.

## 📦 Paso 1: Crear el Repositorio en GitHub

1. Ir a [GitHub](https://github.com) y crear un nuevo repositorio llamado `pokedex`.
2. Clonar el repositorio:
   ```bash
   git clone https://github.com/TU_USUARIO/pokedex.git
   cd pokedex
   ```
3. Copiar dentro del repositorio el código fuente de la aplicación PokeDex disponible en:
   [https://github.com/rcuello/ac4dem1a/tree/master/sistemas-distribuidos/poke-dex-lab](https://github.com/rcuello/ac4dem1a/tree/master/sistemas-distribuidos/poke-dex-lab)

4. Subir los cambios:
   ```bash
   git add .
   git commit -m "Despliegue inicial de PokeDex"
   git push origin main
   ```

## 🌐 Paso 2: Desplegar en Azure Static Web Apps

1. Iniciar sesión en [https://portal.azure.com](https://portal.azure.com).
2. Crear un nuevo recurso: **Static Web App**.
3. Llenar los datos:
   - Nombre: `pokedex-app`
   - Region: `Central US`
   - Fuente: `GitHub`
   - Repositorio: Seleccionar tu repo `pokedex`
   - Rama: `main`
   - Build presets:
     - Si usas HTML/CSS/JS puro → selecciona `Custom`
     - Si usas Angular → selecciona `Angular`
   - App location: `/` o `src`
   - Output location: `dist` o `/`

4. Hacer clic en **Review + Create** y luego en **Create**.

## 🔐 Paso 3: Configurar Encabezados de Seguridad

1. Crear un archivo llamado `staticwebapp.config.json` con el siguiente contenido:

```json
{
  "globalHeaders": {
    "Content-Security-Policy": "default-src 'self'; connect-src 'self' https://pokeapi.co; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; img-src 'self' https://raw.githubusercontent.com data:; font-src 'self' https://fonts.gstatic.com;",
    "X-Frame-Options": "SAMEORIGIN",
    "X-Content-Type-Options": "nosniff",
    "Referrer-Policy": "strict-origin-when-cross-origin",
    "Permissions-Policy": "geolocation=(), camera=(), microphone=()",
    "Strict-Transport-Security": "max-age=63072000; includeSubDomains; preload"
  },
  "navigationFallback": {
    "rewrite": "/index.html"
  }
}
```

2. Si usas Angular, agregarlo al `angular.json`:
```json
"assets": [
  "src/favicon.ico",
  "src/assets",
  "src/staticwebapp.config.json"
]
```

3. Hacer `git add`, `commit` y `push` para que Azure vuelva a desplegar.

## 🔍 Paso 4: Verificar Seguridad

1. Accede a [https://securityheaders.com](https://securityheaders.com)
2. Ingresa tu URL de Azure.
3. Deberías obtener una calificación: ✅ **A+**
