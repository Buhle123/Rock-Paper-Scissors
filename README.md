# Rock, Paper, Scissors: The Final Showdown

A browser-based Rock, Paper, Scissors game against an evil AI. Be the first to win **3 rounds** to save the world.

The game is played with browser pop-ups (`prompt()`, `alert()`, `confirm()`) and the browser **console**. There is no visible content on the page itself.

## How to run

1. Download or clone this project.
2. Open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari).
3. Follow the pop-ups.

> Tip: for the best experience, open the console **before** pressing OK on the intro pop-up (see below).

## How to play

1. Read the intro pop-up and press **OK** to begin (or **Cancel** to leave).
2. In each prompt, type `Rock`, `Paper`, or `Scissors` and press **OK**.
3. The AI picks at random. The round result and score appear in the console and in the next prompt.
4. The first side to win **3 rounds** wins the game.

### Rules

- Rock beats Scissors, Scissors beats Paper, Paper beats Rock.
- **Draws award no points** to either side.
- **Invalid input does not count as a round.** You will see a message and be asked again.
- Input is **case-insensitive** and extra spaces are ignored (`"  PaPeR "` works).
- Pressing **Cancel** at any prompt ends the game safely, with no errors.

## Why the console is needed

The full battle report (what you chose, what the AI chose, who won each round, and the score) is logged in the browser console. The prompts also show the score and last result, and a final pop-up announces the winner, so the game remains playable if the console is closed.

### How to open the console

| Browser / OS | Shortcut |
|---|---|
| Chrome, Edge, Firefox (Windows/Linux) | `F12`, then click the **Console** tab (or `Ctrl + Shift + J` in Chrome) |
| Chrome (Mac) | `Cmd + Option + J` |
| Safari (Mac) | Enable the Develop menu in Settings, then `Cmd + Option + C` |

## Project structure

```
rock-paper-scissors/
├── index.html   # Blank page that loads the script
├── script.js    # All game logic
└── README.md
```

## Code overview

| Function | Purpose |
|---|---|
| `computerPlay()` | Randomly returns `"Rock"`, `"Paper"`, or `"Scissors"` |
| `getPlayerSelection()` | Prompts the player, cleans the input, re-asks on invalid input, returns `null` on Cancel |
| `playRound(playerSelection, computerSelection)` | Returns `"player"`, `"computer"`, or `"draw"` (it does not log anything) |
| `showIntro()` | Explains the story, rules, and console instructions |
| `game()` | Runs the loop, tracks the score, and announces the final winner |

A `WINNING_SCORE` constant controls how many wins are needed.

## Testing checklist

- [ ] `rock`, `ROCK`, and `  Rock  ` are all accepted
- [ ] Empty input and random text show an error and do not change the score
- [ ] Draws do not change the score
- [ ] Cancel works on the intro and on every move prompt
- [ ] Game ends at exactly 3 wins for either side
- [ ] Final result appears in both the console and a pop-up
- [ ] Someone who has never seen the code can start and play without help

## Known notes

- A console message such as `Unsafe attempt to load URL ... 'file:' URLs are treated as unique security origins` can appear when opening the page from disk. It is a harmless browser message and does not come from the game code.
- To play again, refresh the page.
