# Netherak Demons — contexto para Claude

Maqueta web inmersiva (estilo Minecraft) que valida el loop core: **entrar → mirar → detectar NPC al hover → leer panel**. El plan completo está en `netherak-maqueta-plan.md`.

## Arquitectura (importante)

- **Todo vive en un único `index.html` autónomo (~750 KB).** No hay build, ni `node_modules`, ni servidor: abre con doble clic, sin conexión.
- **three.js r184 está incrustado dentro del HTML**, no por CDN. Va en dos `<script type="text/plain">` (`core` + `module`, minificados). El script de módulo los convierte en `Blob` URLs y **parchea el import relativo** `./three.core.min.js` → blob del core, para que el ES module resuelva bajo `file://`. Hay respaldo a CDN si se quitaran esos bloques.
- Capas del código (en orden, comentadas dentro del archivo): **Cuarto → Cámara** (arrastrar para mirar, no pointer-lock) **→ NPCs** (pila base/cuerpo/cabeza) **→ Hover** (raycast desde el cursor) **→ Panel**.
- NPCs (Malphavor/rojo, Ysthrea/teal, Nerathul/violeta) con `emissive` base tenue que sube + luz propia al hacer hover. **Antorchas** en las paredes (luz cálida con parpadeo) para iluminar la sala.

## Cómo editar y probar

- Editá `index.html` directamente. El bloque grande de texto plano al inicio del `<head>` es three.js incrustado: **no lo edites a mano**; si hay que actualizar three, reemplazá esos dos bloques con `three.core.min.js` + `three.module.min.js` del build deseado.
- Para ver cambios: doble clic en `index.html`. La verificación automatizada se hizo con Playwright cargando la página bajo `file://` (render WebGL, hover, clic→panel, cerrar, arrastre).

## Pendiente (siguiente iteración del plan)

Animaciones de personajes, partículas/fuego, loading screen, audio, mobile/touch, lore real, iluminación más elaborada y modelos 3D importados.
