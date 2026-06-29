# Code Architecture Reference

## Overview

The game is a self-contained single-file HTML5 application (`index.html`).

## Key JavaScript Objects

### PETS Array
```js
{
  id: 'emberfang',
  name: 'Emberfang',
  type: 'fire',
  stats: { hp: 110, atk: 30, def: 15, spd: 25 },
  ability: { name: 'Inferno Strike', cooldown: 3 },
  color: '#FF3B30'
}
```

### GameState Object
```js
{
  screen: 'start' | 'select' | 'battle' | 'defeated',
  playerPet: Pet,
  enemyPet: Pet,
  turn: 'player' | 'enemy',
  round: Number,
  log: String[]
}
```

### Rendering Loop
```js
function gameLoop(timestamp) {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  update(timestamp);
  render(timestamp);
  requestAnimationFrame(gameLoop);
}
```

## Adding a New Pet

1. Add entry to `PETS` array with all fields
2. Add case to `renderPetSprite(ctx, pet, x, y)`
3. Add ability logic to `executeAbility(pet, target)`
4. Balance-test against all existing pets
