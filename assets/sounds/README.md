Dejá acá los archivos de audio con estos nombres exactos (case-sensitive).
Formato recomendado: `.mp3` (liviano, soportado en todos los navegadores
móviles). El sistema ya está conectado (ver `src/sound-manager.ts` y
`src/sound-clip.ts`) — apenas exista el archivo con el nombre correcto,
suena solo, no hace falta tocar código.

## Generales (1 sola vez, no por personaje)

- `music-intro.mp3` — música de fondo fuera de combate (lobby, colocar
  cartas, revelación, resultado de ronda/partida). Loop.
- `music-combat.mp3` — música de fondo durante el combate. Loop.
- `sfx-victory.mp3` — efecto al ganar la partida (no por ronda).

## Por personaje (characterId de card-target, ver src/.expanse.json)

Para cada uno de: `batman`, `superman`, `wonderwoman`, `flash`, `cyborg`,
`joker`, `harley`:

- `sfx-attack-<characterId>.mp3` — se reproduce cada vez que ese personaje
  golpea (ej. `sfx-attack-batman.mp3`).
- `sfx-death-<characterId>.mp3` — se reproduce cuando ese personaje cae
  (ej. `sfx-death-batman.mp3`).

## Si querés agregar un sonido nuevo que no esté en esta lista

1. Poné el .mp3 acá.
2. En Studio, agregá una entidad con un componente `audio` (Properties
   panel) apuntando a `assets/sounds/tu-archivo.mp3`, y otro componente
   `sound-clip` con el `clipId` que quieras usar.
3. Llamá a `playMusic`/`playVictorySfx`/`playCharacterSfx` (o agregá una
   función nueva en `sound-manager.ts`) usando ese mismo `clipId`.
