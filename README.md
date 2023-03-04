# falbot-snake

NPM Package to play the snake game on discord

## Usage

```Node
const snake = require("falbot-snake")

//initiate the game
const game = new snake.Game()

//move the snake in all four directions
game.snakeMovement(game.snake, "N")
game.snakeMovement(game.snake, "W")
game.snakeMovement(game.snake, "E")
game.snakeMovement(game.snake, "S")

//get the game field
game.world2string(game.world, game.snake)

//you can automatically move the snake in the last direction moved when the time expires
var myTimer = setInterval(async function () {
    if (game.time <= 0) {
        game.snakeMovement(game.snake, game.Sd)
        game.time = 30
    }

    game.time -= 5
}, 1000 * 5)

//check if the game has ended
if (game.gameEnded) {
    console.log('end')
}

```
