# Arduino LED Strip Timing Game (Cyclon Game)

This is a **reaction/timing game** for Arduino using WS2812B ("NeoPixel") LED strips.  
Inspired by code from Mirko Pavleski, this version adds levels, effects, and a separate LED "score" display.

## Features

- **WS2812B (NeoPixel) LED Strip**: Main display with 60 individually-addressable LEDs.
- **Score LEDs**: Separate 8-LED strip to show progress/level.
- **Single Button Control**: All game interaction via one push button.
- **Multiple Levels**: Speed increases with each level.
- **Random Target Zones**: Each round, a new target appears at a random location on the LED strip.
- **Reaction Challenge**: Press the button when the moving white light overlaps the target zone!
- **Visual Feedback**: Success and failure animations with colors and effects.
- **Easy Restart**: Game resets after each win or loss.
- **Sound Support**: (Commented out, can be enabled if buzzer is added.)

## Hardware Requirements

- **Arduino UNO, Nano, Mega** or compatible board
- **WS2812B LED Strip (60 LEDs)** — main game display
- **WS2812B LED Strip (8 LEDs)** — score/progress display
- **Push Button** (connected to pin 5 with pull-up)
- **(Optional) Buzzer** on pin 9 (for sounds, code commented out)
- **Power supply** for LED strips (recommended)
- **Jumper wires, breadboard, or PCB**

## Pinout

| Function           | Arduino Pin |
|--------------------|:-----------|
| LED Strip (60)     | A0         |
| Score LED Strip (8)| 6          |
| Button             | 5          |
| (Optional) Buzzer  | 9          |

*Change `DATA_PIN`, `SCORE_PIN`, and `BUTTON_PIN` in the code if you use different pins.*

## Libraries Needed

- [FastLED](https://github.com/FastLED/FastLED)

Install via the Arduino Library Manager.

## How to Play

1. **Power up the game:** The LED strip shows a rainbow idle animation.
2. **Start a round:** Press the button. The LED strip clears, and a moving white light starts from the beginning.
3. **Target zone:** Each round, a random green target appears somewhere on the strip (orange for boundaries).
4. **React!** Press the button when the moving light is in the green zone.
    - If you succeed: The score/progress LED advances, and you move to the next level (faster).
    - If you fail: Red "loser" animation, game resets to idle.
5. **Levels:** The speed increases with each round up to 8 levels. If you win all levels, the game resets.
6. **Try again!** See how far you can go and how fast your reflexes are!

## Game States

- **Idle/Ready:** Rainbow animation, waiting for button press.
- **Active Level:** Moving white light, press button at the right time!
- **Win:** Green animation, progress LED advances, speed increases.
- **Lose:** Red animation, game resets.

## Customization

- Change `NUM_LEDS` and `SCORE_LEDS` for different strips.
- Adjust the `ledSpeed` array for game speed per level.
- Uncomment `tone(...)` lines and connect a buzzer for sound effects.

## Credits

- Based on code by Mirko Pavleski

## License

This project is open source. See the `LICENSE` file for details.

---

Have fun and train your reflexes!
