# 🧢 Proyecto PokeDex - Azure Static Web Apps

Este repositorio contiene el código fuente y documentación para el despliegue seguro de la aplicación **PokeDex** en la nube utilizando **Azure for Students**.

## 👨‍💻 Descripción del Proyecto

**PokeDex** es una aplicación web que permite explorar diferentes especies de Pokémon, consultando sus estadísticas, tipos y habilidades a través de la PokéAPI. La interfaz está diseñada para ser clara, interactiva y educativa.

## 🛠 Tecnologías Usadas

- HTML5, CSS3, JavaScript
- [PokéAPI](https://pokeapi.co/)
- Git y GitHub
- Azure Static Web Apps
- Encabezados de seguridad HTTP (CSP, HSTS, etc.)

## 🧾 Creación de la Cuenta en Azure for Students

1. Accede a: [https://azure.microsoft.com/en-us/free/students/](https://azure.microsoft.com/en-us/free/students/)
2. Haz clic en el botón **"Start free"**.
3. Inicia sesión con tu **correo institucional universitario**.
4. Llena el formulario con tus datos personales.
5. Acepta los términos y condiciones.
6. Confirma la verificación académica (puede ser automática o manual).
7. Una vez validada tu cuenta, tendrás acceso a los recursos gratuitos de Azure.

## 📂 Estructura del Repositorio

```
pokedex/
├── index.html
├── styles.css
├── script.js
├── staticwebapp.config.json
├── README.md
└── Despliegue.md
```

## ✅ Seguridad

Para garantizar una buena puntuacion en [SecurityHeaders.com](https://securityheaders.com), se añadieron encabezados HTTP seguros en el archivo `staticwebapp.config.json`.

Incluye:

- `Content-Security-Policy`
- `Strict-Transport-Security`
- `X-Frame-Options`
- `X-Content-Type-Options`
- `Referrer-Policy`
- `Permissions-Policy`

## 🔗 Enlace a la Aplicación en Producción

https://ashy-river-0f6dc211e.6.azurestaticapps.net/
