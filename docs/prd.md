# PRD: Sistema de Notas y Etiquetas (Inspirado en Google Keep)

**Versión:** 0.1.0 (Borrador inicial - Sprint 0)  
**Autor:** Javier Pernía  
**Materia:** Lenguaje de Programación · 2026  

---

## 1. Visión del Producto y Problema a Resolver
El proyecto consiste en una aplicación web integral para la captura rápida, organización y recuperación de notas mediante un sistema de etiquetas dinámicas, tomando como referencia de diseño y experiencia de usuario a **Google Keep**.

A diferencia de las herramientas convencionales que imponen taxonomías rígidas de carpetas o formatos pesados, este sistema prioriza:
- Captura de baja fricción (notas rápidas en pocos clics).
- Distribución visual fluida tipo cuadrícula dinámica (*masonry*) y lista.
- Organización transversal mediante etiquetas multidimensionales.

---

## 2. Alcance Funcional Base (Inspirado en Google Keep)
1. **Gestión de Notas:**
   - Crear, editar, visualizar y eliminar notas con título y cuerpo.
   - Fijar notas importantes en la parte superior del muro (*pinned*).
   - Cambio de colores/temas para clasificación visual rápida.
   - Soporte para listas de verificación (*checklists*) con ítems tachables.
2. **Ciclo de Vida y Estados:**
   - **Activas:** Visibles en el muro principal.
   - **Archivadas:** Ocultas del muro diario pero accesibles para consulta.
   - **Papelera:** Eliminación lógica (*soft delete*) con posibilidad de restauración o purga definitiva.
3. **Taxonomía por Etiquetas:**
   - Creación, edición y eliminación de etiquetas.
   - Asociación de múltiples etiquetas a una misma nota (relación N:M).
   - Navegación lateral para filtrado instantáneo por etiqueta seleccionada.

---

## 3. Propuesta de Valor y Funcionalidades Diferenciales
Para superar las limitaciones conocidas de Google Keep, este sistema incorporará:
1. **Soporte Nativo de Markdown:** Renderizado estructurado de encabezados, negritas, listas y bloques de código dentro del cuerpo de la nota.
2. **Búsqueda Avanzada de Texto Completo:** Indexación especializada en PostgreSQL para búsquedas instantáneas y precisas por palabras clave.
3. **Historial de Modificaciones:** Registro de versiones para auditar cambios y prevenir pérdidas accidentales de información.

---

## 4. Arquitectura y Tecnologías
- **Frontend:** HTML5, CSS3 moderno, TypeScript (carpeta `clon/` en Sprint 1 y aplicación final).
- **Backend:** Node.js 24 + Express en TypeScript estricto bajo *Screaming Architecture*.
- **Persistencia:** PostgreSQL en contenedor Docker, con migraciones SQL manuales en `db/migrations/` y tablas:
  - `notes` (id, title, content, color, is_pinned, is_archived, deleted_at, timestamps).
  - `labels` (id, name, color, timestamps).
  - `notes_labels` (note_id, label_id).
  - `checklist_items` (id, note_id, text, is_completed, position).
- **Aseguramiento de Calidad:** Vitest para pruebas unitarias/arquitectura y Playwright para pruebas E2E.
