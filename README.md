# ☕ Sr. Coffee

Chatbot conversacional local con diseño de cafetería.

## Estructura

```
SrCoffee/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.jsx              ← punto de entrada
    ├── App.jsx               ← orquestador del flujo
    ├── data/
    │   ├── topics.js         ← temas, respuestas, starters
    │   └── icons.jsx         ← iconos SVG reutilizables
    └── components/
        ├── Landing.jsx       ← presentación con scroll
        ├── Login.jsx         ← login + carga animada
        ├── Onboarding.jsx    ← preguntas de bienvenida
        └── SrCoffee.jsx      ← chat principal
```

## Flujo

```
Landing → Login (coffeelover / 1234) → Onboarding → Chat
```

## Instalación

```bash
npm install
npm run dev
```

Abre http://localhost:5173

## Credenciales

- Usuario: `coffeelover`
- Contraseña: `1234`

## Para conectar Gemini (opcional)

Si quieres respuestas reales vía API, puedes reemplazar
la función `getResponse()` en `SrCoffee.jsx` con una
llamada a tu backend Express en `localhost:3001`.
