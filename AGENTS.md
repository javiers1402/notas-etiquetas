# AGENTS.md - Sistema de Notas y Etiquetas (Inspirado en Google Keep)

## 📌 Visión del Producto
Aplicación web integral para captura rápida, organización visual fluida y recuperación de información mediante notas y etiquetas dinámicas, tomando como referencia directa de diseño y experiencia de usuario a **Google Keep**.

## 👥 Usuarios Objetivo
Estudiantes, profesionales y usuarios cotidianos que requieren un espacio ágil y sin fricciones para registrar ideas, listas de pendientes y recordatorios con clasificación multidimensional.

## 🧱 Alcance y Funcionalidades
1. **Notas:** Crear, editar, archivar, fijar (*pinned*), cambiar colores/temas y papelera con borrado lógico (*soft delete*).
2. **Listas de Verificación:** Soporte para ítems tachables dentro de la nota.
3. **Etiquetas:** Creación de etiquetas y asignación múltiple (relación N:M).
4. **Diferenciales:** Soporte de formato Markdown, búsqueda full-text optimizada en PostgreSQL e historial de modificaciones.

## 🛠️ Stack Tecnológico y Arquitectura
- **Frontend:** HTML5, CSS3 moderno, TypeScript (carpeta `clon/` en Sprint 1 y SPA final).
- **Backend:** Node.js 24 + Express en TypeScript estricto bajo *Screaming Architecture*.
- **Persistencia:** PostgreSQL en contenedor Docker (`db/migrations/`).
- **Calidad:** Vitest para pruebas unitarias/arquitectura y Playwright para pruebas E2E.
