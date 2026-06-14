#  Sr. Coffee

Chatbot conversacional con diseño de cafetería. Flujo completo de Landing → Login → Onboarding → Chat, con respuestas vía Gemini y modo local de respaldo.

---

# Características

- Landing con scroll animado y demos de conversación
- Login temático con animación de carga
- Onboarding con preguntas de bienvenida
- Chat con 6 temas de conversación distintos
- Modo claro / oscuro
- Sistema de racha diaria, cafés y sesiones
- Check-in de estado de ánimo
- Panel de analíticas y perfil de usuario
- Respuestas vía Gemini (IA real) con fallback local si no hay conexión o API key

---

# Estructura

```
SrCoffee/
├── api/
│   └── chat.js              ← Serverless Function (Vercel) que llama a Gemini
├── index.html
├── package.json
├── vite.config.js
├── .env.example
└── src/
    ├── main.jsx
    ├── App.jsx               ← orquestador del flujo
    ├── data/
    │   ├── topics.js         ← temas, respuestas locales, starters
    │   └── icons.jsx
    └── components/
        ├── Landing.jsx
        ├── Login.jsx
        ├── Onboarding.jsx
        └── SrCoffee.jsx       ← chat principal
```

---

# Instalación local

```bash
npm install
npm run dev
```

Abre **http://localhost:5173**

# Credenciales de acceso (Login)

- Usuario: `coffeelover`
- Contraseña: `1234`

---

# Conectar Gemini (respuestas reales con IA)

La app funciona **sin configurar nada** (usa respuestas locales predefinidas).
Para que Sr. Coffee converse de verdad con Gemini, sigue estos pasos:



##  Cómo funciona el fallback

`SrCoffee.jsx` intenta llamar a `/api/chat` (Gemini). Si:
- No hay `GEMINI_API_KEY` configurada, o
- Falla la conexión, o
- Se agota la cuota gratuita

...la app cae automáticamente a respuestas locales predefinidas en `src/data/topics.js`, sin romperse ni mostrar errores al usuario.

---


---

##  Stack

- React 18 + Vite 5
- Vercel Serverless Functions
- Gemini 2.0 Flash API
- CSS-in-JS (sin librerías de estilos externas)
