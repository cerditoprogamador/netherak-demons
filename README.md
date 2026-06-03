# Netherak Demons — Maqueta

Maqueta web inmersiva: una escena 3D *blocky* (estilo Minecraft) que valida el loop core del juego — entrar a un cuarto, mirar alrededor, detectar personajes al pasar el cursor y leer su info al hacer clic.

![estado](https://img.shields.io/badge/estado-maqueta_validada-success)

## Cómo abrirla

**Doble clic en `index.html`.** Funciona **sin conexión y sin instalar nada**: three.js (r184) viene incrustado dentro del propio archivo.

> Si tu navegador bloqueara algo al abrir por `file://`, serví la carpeta:
> ```bash
> python3 -m http.server 8000
> ```
> y abrí http://localhost:8000

## Controles

| Acción | Resultado |
|---|---|
| **Arrastrar** | Mirar alrededor (gira la vista) |
| **Acercar el cursor** a una figura | Se ilumina y aparece su nombre |
| **Clic** sobre la figura | Abre el panel de información |
| **×** o **Esc** | Cierra el panel |

Hay 3 personajes en la sala: dos al frente y **uno a tu espalda** (giralo para encontrarlo).

## Estructura

- `index.html` — la maqueta completa, **un solo archivo autónomo** (~750 KB con three.js incrustado).
- `netherak-maqueta-plan.md` — el plan original de la maqueta.
- `CLAUDE.md` — contexto del proyecto para Claude Code.

## Siguiente iteración (fuera de alcance de esta maqueta)

Animaciones de personajes, partículas, loading screen, audio, mobile/touch, lore real y modelos 3D importados.
