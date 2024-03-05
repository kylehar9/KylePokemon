

# Requirements
### File structure
├── README.md
├── images
├── Team_Rocket.png
├── beauty.png
├── biker.png
├── bird_keeper.png
├── blackbelt.png
├── bug_catcher.png
├── burglar.png
├── fisherman.png
├── hiker.png
├── lass.png
├── psychic.png
├── super_nerd.png
└── youngster.png
├── index.html
├── loading-bar.css
├── loading-bar.js
├── poke.css
├── pokemon.js
├── prompt.txt
└── prompt_parsed.md


### Files to focus on
- index.html - add JS to the script tags

### Files NOT to modify
- poke.css
- pokemon.js
- images.zip
- loading-bar.css
- loading-bar.js

## TODO
- [x] loading-bar subdir
  - copy loading-bar js & css into it
- [x] 2 global vars for trainers
- [x] Person class(params)
  - constructor()
  - firstName
  - lastName
- [x] Pokemon class
  - constructor(name, type, image)
  - name
  - type
  - image
  - healthPower (100)
  - updateHP(this.healthPower)
  - [ ] Also call load bar to update with the HP value.
    - `bar1.set(this.healthPower);`
- [x] Trainer class
  - Inherits from Person
    - constructor(firstName, lastName, type)
  - type
    - Bug Cather, Hiker, etc.
    - from trainer select box.
  - party
    - the team of Pokemon objects
  - currPokemon
  - currPokemonIndex
    - Pokemon 1, 2, or 3
  - wins
  - losses
    - updated at the end of completed game.
  - nextPokemon()
    - update this.currPokemonIndex
    - try to exceed?
      - assign value `null` to currPokemon.
  - clearParty()
    - reset party array.
  - addPokemonToParty(Pokemon)
    - this.party.push(Pokemon)
- [ ] Battle()
  - On start
    - Restart button hidden
  - On end
    - Attack button is hidden
    - Restart button displayed

### Flow
1. I enter team info
2. I pick my team
3. I click BATTLE
4. I click ATTACK
   - Does attack for both sides
   - User keeps clicking it
5. Victory
   - One side has all pokemon at 0
     - (Current pokemon is null)
   - Winner determined.

### ~~My team~~
- [x] firstname & lastname required fields
- if not added
    - give error
    - set focus to empty one
- if added
    - don't set focus to input.
- [x] Read 1st, 2nd, & 3rd input boxes and trainer box for my team.
- 
### ~~Opponent team~~

- Has copy of his own tags
  - Update as it goes
- [x] Attributes
  - [x] Pokemons: random numbers 
  - [x] Img: Will always be Team Rocket
  - [x] First name: always be "Team"
  - [x] Last name: always be "Rocket"
  - [x] Type is always "Team Rocket"

### ~~On start~~
- When have Pokemon party
    - for each Pokemon display image + name
    - For trainer display
        - image
        - name
        - wins
        - losses
### Restart
- reset HP in each Party to 100
- reset each Trainer's pokemon index to 0
- clear displays & hide Restart button.

### Attack
- My first pokemon attacks his first pokemon
- If health goes to 0, either side, it goes to next index
- My pokemon attacks
  - Display active pokemon's name & "attacks!" in move box

### Faint
- Health hits 0
- Display active pokemon's name & "fainted!" in move box

### Endgame
- [ ] Results box with p tag
  - "Team Rocket wins!"
- [ ] Update wins & losses for each trainer object


### HP modification
- let damage = 10
- let effectiveness
  - calculateEffectiveness(myType, oppType)
  - switch
    - case()
      Type == Type then return .5
      Fire vs Water then return .5
      Fire vs Grass then return 1.5
      Water vs Fire then return 1.5
      Water vs Grass then return .5
      Grass vs Fire then return .5
      Grass vs water then return 1.5
      Otherwise return 1
  - 1.5 = "It was super effective!"
  - .5 = "It was not very effective..."
    - goes to `myEffectiveness` html in DOM
  - [ ] Critical hits
    - random weight 0 =< x < 1
      - x>= .9 
        - "Critical Hit" in `myExtra` html DOM
      - x <= .1
        - "But it missed..."
        - write "" to `myEffectiveness` html in DOM
  - [ ] damage power = damage * effectiveness * multiplier
    - modifies HP
    - passed to class method
      - I attack? update opp HP
      - He attack? update my HP
  - 




---
Use the following provided files for creating your Pokemon Battle website. Make sure you follow the directions for downloading the files and putting them in the correct folder.

Create a folder called finalExam. Download the index.html file and place it in that folder.

NOTE: You should be able to right mouse click on the link and choose Save Link As and then it will save the files.

index.html Download - This is the html file. You will NOT need to modify the html tags BUT you WILL need to add your JavaScript in the SCRIPT tags.

poke.css Download - Contains the CSS needed. DO NOT MODIFY

pokemon.js Download - Contains the data you will read to load up random pokemons. DO NOT MODIFY. You will use this file when you randomly select pokemons and also for your selected pokemons in the select box. The file indicates the order of the data and what it means. It is an array of data with each data being another array. You will use that data when creating Pokemon objects.

images.zip Download - Contains the images for the pokemons. DO NOT MODIFY

loading-bar.css Download - Contains the CSS needed for the loading bar. DO NOT MODIFY

loading-bar.js Download - Contains the JavaScript needed for the loading bar. DO NOT MODIFY


In your project folder finalExam create a sub-folder called images and unzip the images.zip file in that folder

In your project folder finalExam create a sub-directory called loading-bar and copy the loading-bar.css and loading-bar.js files in that folder

Your job will be to write the necessary JavaScript code to finish the Pokemon Battle website. When completed, the battle screen will look as follows upon initial start:



First name and last name are required fields. If they do not enter those, display a message and set focus to which ever one is empty. If it is not empty do not set focus to that input.

After filling in the required form information, the user will click on the Go Battle button to begin the game. You will need to generate random numbers to load up the opponent's pokemons from the array of data in the pokemon.js file. You will read the First, Second, and Third pokemon select boxes to load up your team of pokemon objects. You will also select your trainer from the select box.

Using the form data, you will create your team array of pokemon objects and the opponents team array of pokemon objects (NOTE: The opponent Trainer will always be Team Rocket and will use the Team_Rocket.png file for the image). You are also creating both Trainer objects. The opposing team first name will always be "Team" and the last name will be "Rocket" and the type will be "Team Rocket". Generate random numbers to select the opponent's Pokemon's in the team (Party).

The user will click on the Attack button and will see something like:



NOTE: One click of the attack button does your attack and the opponents attack.

Your first pokemon object in your team will attack the opponent's first pokemon object. Each object starts with a health power of 100. As you attack you will generate a hit power and possibly reduce your opponent's health power. Then they will attack and possibly reduce your pokemon's health power. If your pokemon's health power goes down to 0 (or less) then your new active pokemon will be the next pokemon object in your team. The same applies for the opponent's pokemon. If the health power for the current pokemon hits 0 then you move on to the next pokemon. In other words, you will need to keep track of the trainer's current pokemon for each team. Once that pokemon faints, then you have to update or move on to the next pokemon and make it the current pokemon to battle.

The user will continue to click on the Attack button until either the user or the computer wins the battle. Once one of the team runs out of pokemon's (All of their pokemon's health have hit 0 and they have fainted and the current pokemon is null), then the game is over and the winner is determined.

When your pokemon attacks, you will display your active pokemon's name and the word "attacks!" in your move box. If your pokemon's health hits 0 then you will display your pokemon's name and the word "fainted!" in the same box. There are 4 paragraph tags in each box display (myMove, myEffectiveness, myExtra, and myFainted). You will be dynamically updating these tags as the game is being played.

The opponent also has a copy of their own tags and you will update those as the game is played.

The results box has a p tag that will display the final results when the game is over (i.e. Team Rocket wins!). You will display the trainer's name and "wins!". You will then update the wins and losses for each trainer object for each game completed.

You will want to create 2 global variables (one for each trainer).

Create a Person class with the attributes of firstName and lastName. Make sure you create the proper constructor that receives params.

Create a Pokemon class with the attributes of name, type, image, and healthPower. Create the appropriate constructor that receives the name, type, and image. The healthPower attribute will be initially set to 100.

Create a method in the Pokemon class that receives the new healthPower and you will update your healthPower attribute for the object. Also call the load bar to update it using the healthPower value.

bar1.set(this.healthPower);

Create a Trainer class that inherits from Person. It adds the following attributes: type, party, currPokemon, currPokemonIndex, wins, and losses.

Make sure you make the appropriate constructor that receives the first name, last name, and type.

The party attribute will end up being an array of Pokemon objects (that is the team). The type is the type of trainer (i.e. Bug Catcher, Hiker, etc.) from the Trainer select box. The currPokemon keeps track of your current Pokemon that is battling. The currPokemonIndex keeps track of which Pokemon is battling (1, 2, or 3). The wins and losses are updated at the end of each completed game.

Create a method called addPokemonToParty that receives a pokemon object and adds it to the party attribute for the Trainer object.

Create a method called nextPokemon which updates the currPokemonIndex attribute when called. If you try to exceed the count of the party array then assign the value of null to the currPokemon.

Create a method called clearParty that resets the party array.

Create a battle function. When the battle is first started, the Restart button should be hidden. When the battle is completed, the Attack button is hidden and the Restart button is displayed.

Make sure that after you create your Pokemon parties, for each Pokemon you display the associated image and name. For the trainer you will display the associated image, name, wins, and losses. You will do this for your party and your opponent's party.

HOW THE HEALTH POWER IS MODIFIED:

When you attack you have to calculate the level of your effectiveness. I had a variable called damage and gave it a value of 10. The effectiveness is calculated by calling a function called calculateEffectiveness. This function receives each of the current Pokemon's type for your party and the opponent's party.

Type == Type then return .5
Fire vs Water then return .5
Fire vs Grass then return 1.5
Water vs Fire then return 1.5
Water vs Grass then return .5
Grass vs Fire then return .5
Grass vs water then return 1.5
Otherwise return 1

Use this value to determine the Effectiveness display for each attack. If the value is 1.5 then display "It was super effective!". If the value is .5 then display "It was not very effective...". Write this to the myEffectiveness html object using the DOM.

Generate a random multiplier number between 0 and 1 (do NOT include the number one though). If the multiplier value is >= .9 then write "Critical Hit" to the myExtra html object using the DOM. If the multiplier value is <= .1 then write "But it missed..." to the myExtra html object and write an empty string to the myEffectiveness html object instead of the "It was super effective!" or "It was not very effective..."

Calculate the damage power to the health for the Pokemon by using the formula:
damage * effectiveness * multplier

This value is used to modify the health power and is passed to the appropriate class method to update the opponent's health power if you attack. Update your health power if the opponent attacks.

In other words, your Pokemon will attack, update the opponent's health and then will attack and update your Pokemon's health.

Continue this process until a pokemon faints (healthPower = 0). Once that pokemon's healthPower = 0 then move on to the next pokemon in the party. If a party runs out of pokemons then the other party wins.


Display an appropriate winning message and update the wins and losses attributes for each trainer.

Note that when the battle is over the Attack button is hidden and the Restart button is displayed

The Restart button will reset the healthPower in each of the Parties to 100 and reset each of the trainer's current pokemon's index to the first element. It will also clear the displays and hide the Restart button.

The html file does not need to be changed except for adding your JavaScript. I would suggest that you do not modify it. Do not create more files.

Once completed, PASTE your code from your html file which will contain your html AND JavaScript code. DO NOT CREATE A NEW JavaScript file for your new code. Write your JavaScript in the Script tag in the html file.

Make sure you have used appropriate comments!

Hope this was fun! Have a great break!