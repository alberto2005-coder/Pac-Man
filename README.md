# Pac-Man en HTML, CSS y JavaScript

[Español](#español) · [English](#english)

---

## Español

### Índice

- [Descripción](#descripción)
- [Características](#características)
- [Cómo jugar](#cómo-jugar)
- [Puntuación](#puntuación)
- [Fantasmas](#fantasmas)
- [Requisitos](#requisitos)
- [Cómo ejecutar](#cómo-ejecutar)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Cómo funciona](#cómo-funciona)
- [Licencia](#licencia)

### Descripción

Recreación de **Pac-Man** en el navegador con **HTML, CSS y JavaScript puro**, sin frameworks ni dependencias. El laberinto es una cuadrícula de 21 × 21 celdas dibujada con `div`, y los cuatro fantasmas tienen personalidades distintas, como en el arcade original.

### Características

- **Laberinto de 21 × 21** con puntos y *power pellets*.
- **Túnel lateral**: salir por un borde te hace aparecer por el contrario.
- **4 fantasmas con IA propia** (Blinky, Pinky, Inky y Clyde).
- **Modos scatter/chase** alternos, con cambio de dirección al cambiar de modo.
- **Power pellets**: durante unos segundos los fantasmas huyen y se pueden comer.
- **3 vidas** y marcador en tiempo real.
- **Victoria** al comer todos los puntos.
- **Sin dependencias**: se abre directamente en el navegador.

### Cómo jugar

1. Pulsa **INICIAR JUEGO**.
2. Mueve a Pac-Man con las **flechas del teclado**.
3. Come todos los puntos para ganar.
4. Evita a los fantasmas; si te tocan, pierdes una vida.
5. Al comer una *power pellet* grande, los fantasmas se vuelven azules y puedes comerlos.

El botón cambia a **REINICIAR JUEGO** para empezar una partida nueva.

### Puntuación

| Acción | Puntos |
|---|---|
| Punto normal | 10 |
| Power pellet | 50 |
| Comer un fantasma asustado | 200 |

### Fantasmas

| Fantasma | Color | Comportamiento |
|---|---|---|
| **Blinky** | Rojo | Persigue directamente a Pac-Man |
| **Pinky** | Rosa | Se adelanta 4 casillas en la dirección de Pac-Man para emboscarlo |
| **Inky** | Cian | Usa la posición de Blinky y la de Pac-Man para calcular un objetivo vectorial |
| **Clyde** | Naranja | Alterna persecución y patrulla |

Cuando están asustados huyen hacia una esquina aleatoria.

### Requisitos

Solo un navegador moderno (Chrome, Firefox, Edge o Safari).

### Cómo ejecutar

Abre `index.html` en el navegador. También puedes servirlo:

```bash
python -m http.server 8000
```

y visitar `http://localhost:8000`.

### Estructura del proyecto

```text
Pac-Man/
├── index.html    # Marcador, tablero y botón de inicio
├── script.js     # Laberinto, movimiento, IA y colisiones
├── styles.css    # Estilos del tablero y de los sprites
├── logo.png      # Favicon
├── LICENSE
└── README.md
```

### Cómo funciona

- `maze` es una matriz de 21 × 21: `1` pared, `0` punto, `2` power pellet y `3` celda vacía.
- `gameLoop()` se ejecuta cada 300 ms, mueve a los fantasmas cada dos ciclos y redibuja el tablero.
- `getGhostTarget()` devuelve el objetivo de cada fantasma según su nombre y el modo actual.
- `checkCollisions()` resta una vida si Pac-Man coincide con un fantasma no asustado, o suma 200 puntos si está asustado.
- `checkWin()` cuenta los puntos restantes y muestra la victoria cuando no queda ninguno.

### Licencia

Este proyecto se distribuye bajo la **licencia MIT**. Consulta [LICENSE](LICENSE).

---

## English

### Table of contents

- [Overview](#overview)
- [Features](#features)
- [How to play](#how-to-play)
- [Scoring](#scoring)
- [Ghosts](#ghosts)
- [Requirements](#requirements)
- [How to run](#how-to-run)
- [Project structure](#project-structure)
- [How it works](#how-it-works)
- [License](#license)

### Overview

A browser **Pac-Man** recreation built with **plain HTML, CSS and JavaScript**, with no frameworks or dependencies. The maze is a 21 × 21 grid drawn with `div`s, and the four ghosts have distinct personalities, just like the original arcade game.

### Features

- **21 × 21 maze** with dots and power pellets.
- **Side tunnel**: leaving one edge makes you appear on the opposite one.
- **4 ghosts with their own AI** (Blinky, Pinky, Inky and Clyde).
- **Alternating scatter/chase modes**, with a direction flip on each switch.
- **Power pellets**: ghosts flee for a while and can be eaten.
- **3 lives** and a live score.
- **Victory** by eating every dot.
- **No dependencies**: open it directly in the browser.

### How to play

1. Press **INICIAR JUEGO** (Start).
2. Move Pac-Man with the **arrow keys**.
3. Eat every dot to win.
4. Avoid the ghosts; each hit costs a life.
5. Eating a large *power pellet* turns the ghosts blue, and you can eat them.

The button switches to **REINICIAR JUEGO** (Restart) to start a new game.

### Scoring

| Action | Points |
|---|---|
| Normal dot | 10 |
| Power pellet | 50 |
| Eating a scared ghost | 200 |

### Ghosts

| Ghost | Color | Behavior |
|---|---|---|
| **Blinky** | Red | Chases Pac-Man directly |
| **Pinky** | Pink | Targets 4 tiles ahead of Pac-Man to ambush him |
| **Inky** | Cyan | Uses Blinky's position and Pac-Man's to compute a vector target |
| **Clyde** | Orange | Alternates between chasing and patrolling |

When scared, they run toward a random corner.

### Requirements

Any modern browser (Chrome, Firefox, Edge or Safari).

### How to run

Open `index.html` in your browser. You can also serve it:

```bash
python -m http.server 8000
```

and visit `http://localhost:8000`.

### Project structure

```text
Pac-Man/
├── index.html    # Score, board and start button
├── script.js     # Maze, movement, AI and collisions
├── styles.css    # Board and sprite styles
├── logo.png      # Favicon
├── LICENSE
└── README.md
```

### How it works

- `maze` is a 21 × 21 matrix: `1` wall, `0` dot, `2` power pellet and `3` empty cell.
- `gameLoop()` runs every 300 ms, moves ghosts every other cycle and redraws the board.
- `getGhostTarget()` returns each ghost's target based on its name and the current mode.
- `checkCollisions()` removes a life when Pac-Man meets a non-scared ghost, or adds 200 points if the ghost is scared.
- `checkWin()` counts the remaining dots and shows the victory message when none are left.

### License

This project is released under the **MIT License**. See [LICENSE](LICENSE).
