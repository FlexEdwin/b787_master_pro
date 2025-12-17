# AI CONTEXT INJECTION: B787 Certification Platform

Eres el desarrollador principal de una PWA de certificación aeronáutica.
Lee este contexto antes de escribir una sola línea de código.

## 1. Stack Tecnológico (Estricto)

- **Frontend:** HTML5 Single File + Alpine.js v3 (Global Store Pattern) + Tailwind CSS v3 (CDN).
- **Backend:** Supabase (PostgreSQL). Toda la lógica compleja reside en Stored Procedures (RPCs).
- **Filosofía:** "No Build Tools". Editamos directamente `index.html` y `app.js`. Mobile-First.

## 2. Arquitectura de Datos (Supabase)

- **Tablas:**
  - `bancos` (id, slug, nombre): B787, Inglés, AMOS.
  - `atas` (id, banco_id, nombre): Categorías por banco.
  - `preguntas` (id, banco_id, ata_id, texto, opciones, correcta).
  - `respuestas` (id, user_id, pregunta_id, es_correcta, modo_estudio).
- **Lógica de Negocio (RPCs):**
  - `obtener_general`: Filtra maestría y cuarentena.
  - `obtener_repaso`: Lógica de repetición espaciada (Spaced Repetition).
  - `guardar_respuesta`: Guarda historial y modo.

## 3. Estado de la Aplicación (Alpine Store)

- **Navegación:** `vistaActual` ('inicio' -> 'dashboard' -> 'quiz').
- **Contexto:** `bancoSeleccionado` (UUID), `modoEstudio` ('general' | 'repaso').
- **Quiz Engine:** Carga por lotes (Batch Loading de 50 preguntas). Navegación cliente (`indiceActual`, `siguientePregunta()`).

## 4. Reglas de Desarrollo

- **Idiomas:** Código y comentarios en ESPAÑOL.
- **Estilos:** Tailwind clases utilitarias. UI desacoplada de la lógica JS.
- **Seguridad:** Row Level Security (RLS) activo. Validación visual en cliente, lógica en servidor.

## 5. Tarea Actual

[AQUÍ INSERTARÁS TU SIGUIENTE INSTRUCCIÓN ESPECÍFICA]
