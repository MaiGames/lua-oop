# lua-oop

A simple but powerful OOP library for Lua, fork of [kikito/middleclass](https://github.com/kikito/middleclass).

It features inheritance, metamethods (operators), class variables and weak mixin support.

## Simple Example

```lua
local class = require 'lua-oop'

local Animal = class('Animal') -- The argument 'Animal' is the class name 

function Animal:constructor(legs)

  self.fields.legs = legs
  
end

Animal.static.biped_legs = 2 -- class variable (also admits methods)

function Animal:isBiped()

  return self.fields.legs == Animal.biped_legs
  
end

local Dog = class('Dog', Animal) -- inheritance

function Dog:constructor()

  Animal.constructor(self, 4) -- calling the superclass constructor
  
end

local dog = Dog:new()

print(dog:isBiped()) -- false
```
## Installation

Simply copy the lua-oop.lua file anywhere (e.g. on a lib/ folder). Then write this in any Lua file where you want to use it:

```lua
local class = require 'path/to/file/lua-oop'
```

## License

lua-oop is distributed under the MIT license.


