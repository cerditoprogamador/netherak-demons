# Netherak Demons — Plan de Maqueta

**Objetivo:** Una escena 3D blocky (estilo Minecraft) que valide la experiencia core: entrar a un mundo, mirar alrededor, detectar personajes al acercarse el cursor, y ver info al hacer click. Sin detalle visual, solo la interacción funcionando.

---

## Qué tiene que demostrar la maqueta

1. El usuario entra y está dentro de un cuarto 3D
2. Puede girar la vista con el mouse
3. Hay personajes en la sala
4. Al pasar el cursor cerca de un personaje, algo visualmente indica que es interactivo
5. Al hacer click, aparece un panel con información
6. El panel se puede cerrar y seguir explorando

Nada más. Sin animaciones, sin partículas, sin loading screen. Solo el loop de interacción validado.

---

## Las 5 piezas de la maqueta

### 1. El Cuarto
Una sala simple hecha de cajas/bloques:
- Piso plano oscuro
- 4 paredes
- Techo
- Algunos pilares o bloques decorativos para dar profundidad

El objetivo no es que se vea bien, sino que el usuario sienta que está *dentro* de algo.

### 2. La Cámara en Primera Persona
El usuario mira desde adentro del cuarto. Al arrastrar el mouse, la vista gira horizontalmente y verticalmente, como si moviera la cabeza.

Límites: no puede girar más de 90° hacia arriba/abajo para que no se desoriente.

### 3. Los Personajes (NPCs)
Tres figuras blocky distribuidas en la sala. Cada una es una pila de bloques simple: base, cuerpo, cabeza. Sin detalle.

Cada NPC tiene un color diferente para identificarlo fácilmente.

**Estado normal:** figura oscura, apenas visible.
**Estado hover:** la figura cambia de color o se ilumina. Aparece su nombre en texto sobre ella.

### 4. La Detección de Hover
Un rayo invisible sale desde el centro de la pantalla (o desde el cursor) hacia el mundo 3D. Cuando ese rayo toca a un NPC, activa el estado hover.

Al sacar el cursor, vuelve al estado normal.

### 5. El Panel de Información
Al hacer click sobre un NPC en estado hover, aparece un recuadro de texto en la parte inferior de la pantalla. Muestra:
- Nombre del personaje
- Un párrafo de texto placeholder

Un botón de cerrar lo oculta.

---

## Orden de construcción

```
1. Cuarto    →  "Estoy dentro de algo"
2. Cámara   →  "Puedo mirar alrededor"
3. NPCs     →  "Hay personajes"
4. Hover    →  "Sé cuál es interactivo"
5. Panel    →  "Puedo leer info"
```

Cada paso agrega una capa. Si algo no funciona, se detecta temprano sin haber construido encima.

---

## Lo que NO entra en la maqueta

- Animaciones de personajes
- Partículas o efectos de fuego
- Loading screen
- Música o sonido
- Mobile / touch
- Lore real del juego (todo es placeholder)
- Iluminación elaborada
- Modelos 3D importados

Todo eso va en la siguiente iteración, una vez que la maqueta esté validada.

---

## Cómo se valida

La maqueta está lista cuando alguien que no sabe del proyecto puede:
1. Entrar, mirar alrededor sin instrucciones
2. Encontrar los 3 personajes por su cuenta
3. Hacer click en uno y leer la info
4. Cerrar y abrir otro

Si eso funciona fluido, la maqueta cumplió su objetivo.
