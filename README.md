# ![t-util header](https://user-images.githubusercontent.com/35314624/134764530-afd76999-c665-4d1c-a86d-16d1394dbabd.png)

t-util is table utility for [Lua](https://lua.org) and [Luau (or Roblox Lua)](https://luau-lang.org) that is created to extend Lua's standard table library with additional methods for working with tables. Many of its methods come in the standard libraries for other languages.

## Installation
### For Roblox Studio
Paste this code in your command bar to get t-util in your Roblox place, and then press Enter.
```lua
local HttpService = game:GetService('HttpService'); HttpService.HttpEnabled = true; local source = HttpService:GetAsync('https://raw.githubusercontent.com/Loominagit/t-util/main/t-util.lua'); local script = Instance.new('ModuleScript'); script.Name = 't-util'; script.Source = source; script.Parent = game:GetService('ReplicatedStorage');
```
It will create ModuleScript called `t-util` in `ReplicatedStorage`.
### For Lua projects
You can download the source and put `t-util.lua` in your Lua projects, simple as that.

~~For those whose yelling 'publish it on luarocks!!1!', I don't use it lol, sorry.~~

## Notes
1. If you're using Roblox Studio, you need to require t-util and define it as `table`, as Roblox don't let me wrap built-in objects using metatable.
   ```lua
   -- You may replace the require path to where your t-util is located.
   local table = require(game.ReplicatedStorage['t-util'])
   -- ...
   ```
2. If you're making projects outside of Roblox, you can `require` it without defining it. You can define it if you want, tho.
   ```lua
   -- Defining it still works
   local table = require('./t-util')
   -- ...
   ```
   
   ```lua
   -- even better
   require('./t-util')
   -- ...
   ```

## Examples
```lua
-- Random number generator
require('./t-util')
local numArray = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100}
print(table.randomIpair(numArray)) --> 60
```
```lua
-- Filters scores for people who get a score of 80
require('./t-util')
local scores = {Paul = 75, John = 70, Walker = 90, Bruce = 70, Clark = 69, Stark = 100, Steve = 85}
local function filter(score)
   return score >= 80
end
print(table.filter(scores, filter)) --> {Walker = 90, Stark = 100, Steve = 85}
```
```lua
-- Make a new copy of a table, then insert a new value to the new copy.
require('./t-util')
local people = {'Joe', 'Mama'}
local cloned = table.copy(people)
table.insert(cloned, 'Bob')
print(people) --> {'Joe', 'Mama'}
print(cloned) --> {'Joe', 'Mama', 'Bob'}
```

## Methods
If you're looking for t-util's additional methods, you may open [this link](https://github.com/Loominagit/t-util/wiki/Methods).

## License
This repository is released under MIT License.
