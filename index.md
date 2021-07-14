# Important Stuff, trust!!! :

## Balance between readability, scalability and optimizations
- Although having a performant game is nice, a lot of time can be wasted through applying negligible optimizations while also sacrificing both scalability and readibility. Here's an example of micro optimized code vs regular code

```lua
local InputService = game:GetService("UserInputService")
local Remotes = game.ReplicatedStorage.Remotes -- not using :GetService() because they're afraid of a function call

if 2 < Variable then -- always using "<" because ">" translates to "<"

end

-- vs

local InputService = game:GetService("UserInputService")
local Remotes = game:GetService("ReplicatedStorage").Remotes -- staying consistent with 

if Variable > 2 then -- placing the longer expression at the left is a good convention but you lost 1 nanosecond doe :CCCCCC

end
```
- Readable code is crucial especially when you want to present it to other people(or if you're working in a team) or when you go back to tweak it after a while so its semantics can be analyzed quickly.
```lua
local PascalCase = true
local inconsistent_Casing = true
local function veryUselessFunction()
    local CLD = "short for cooldown"
    if CLD=="1" then
        local pos = Vector3.new(1,1,1)
    end
    return "idk man"
end

-- vs

local PascalCase = true
local InconsistentCasing = false

local function UselessFunction()
     local Cooldown = "Cooldown"

     if Cooldown == "1" then
        local Position = Vector3.new(1, 1, 1)
    end

    return "idk man"
end
```
- Use conventional and idiomatic methods.
```lua
table.insert(Table, "hi") -- good
  
Table[#Table + 1] = "hi" -- bad
```
**Scalibility** : "the ability of a computing process to be used or produced in a range of capabilities."*

## Being stuck
- It's easy to dig yourself in a bottomless pit by taking bad approaches then slapping bandaids constantly and blindly thinking.

- Digging faster in a bottomless pit is useless.

- If you're stuck, open yourself to criticism and feedback.

- Touch some grass will ya?

## Improvement
- If you've written some code, it's a good idea to receive feedback from an outer perspective to further improve it.

- Receiving feedback is great because you can learn something new or discover mishaps.

## DRY(Don't Repeat Yourself)
- Declare a variable for something that you're using multiple times, use loops and functions for repeated tasks, don't use a hundred scripts and use modules to handle the tasks instead.

## Simplify your code
- Keep your code simple and tidy, no need to make your code more complex than needed.

## Comments
- Using comments can help make your code more readable, or the opposite. You'll almost never need to use comments if you're working alone. But if you do, then you should make them as explicit as possible.
