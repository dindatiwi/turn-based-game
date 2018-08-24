#Project 6 by Frontend Path by Openclassrooms.com - turn-based-game
Build a turn-based board game in JavaScript

Technologies: Javascript, jQuery, HTML5, CSS3.

Requirements:
1. Randomly generating the game map with obstacles, players, weapons and available space to move.
2. For each turn, a player can move from one to three boxes (horizontally or vertically) before ending their turn. 
3. If a player passes over a box containing a weapon, they leave their current weapon on site and replace it with the new one.
4. If players cross over adjacent squares, a battle begins.

To play the game check the link below:
https://kpochojka.github.io/turn-based-game/

# Code example

// add components to the map function like obstacles, weapon, players, which is used by 'add' function by their
// function constructor.

function addComponents(itemClass, player) {
    let restOfTiles = tiles;
    let boxes = $('.box');
    let empty = true;
    while (empty) {
        let item = random(mapSize);
        if (player === 1) {
            positionRules = (item % 10 === 0);
        } else if (player === 2) {
            positionRules = (item % 10 === 9);
        } else {
            positionRules = (item % 10 !== 0 && item % 10 !== 9);
        }
        if (positionRules && restOfTiles.includes(item)) {
            boxes.eq(item).addClass(itemClass);
            let index = restOfTiles.indexOf(item);
            restOfTiles.splice(index, 1);
            empty = false;
        }
    }
}

