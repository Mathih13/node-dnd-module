# node-dnd-module
Data model for managing player characters(xp, lvl, class) and parties for DMs


#### Installing dnd-module
using powershell or terminal execute an install via the link:

``` 
  npm install 
```


#### Using dnd-module
To start using the dnd module in your app, add the following code to the top of your JS file:

```javascript
const dnd = require('dnd-module');
```
(note that 'dnd' may be swapped for whatever other variable you want to use)


## Documentation

#### Methods:

<dl>
  <dt>dnd.newCharacter(charName, charClass, xp, level)</dt>
  <dd>Creates, saves and returns a new Character with stats specified. charclass, xp and level can be undefined</dd>
  
  <dt>dnd.newParty(name, members)</dt>
  <dd>Creates, saves and returns a new Party with memebers specified. Constructor can be undefined</dd>

  <dt>dnd.getCharacters()</dt>
  <dd>Returns all characters as an array.</dd>
  
  <dt>dnd.getParties()</dt>
  <dd>Returns all parties as an array.</dd>
  
  <dt>dnd.getCharacter(name)</dt>
  <dd>Returns the first character with matching name</dd>
  
  <dt>dnd.clearDB()</dt>
  <dd>Removes all saved Characters</dd>

</dl>

___
#### Classes
An explanation on specific classes:

*Character*: A player character with: Name, Class, XP, Level

##### Constructor:
```javascript
name, characterClass, xp, level
```

###### Methods:

```javascript
setName(newName) // Set a name for the Character
setXP(value) // Set the xp for the Character
setLevel(value) // Set the level of the Character
```

<br><br><br>
*Party*: A party contains Characters that are members of the party

##### Constructor:
```javascript
name, members // name of the party and members in the party
```

##### Methods:

```javascript
addMember(Character) // Adds a member to the end of the partys list
removeMembers(name) // Removes ALL members matching the name input from the party
```

___

#### Examples:
```javascript
const dnd = require('dnd-module');

var dave = dnd.newCharacter('Dave', 'Barbarian', 100, 1);


var prty = dnd.newParty();
prty.addMember(dave);
```
