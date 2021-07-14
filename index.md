# Important Stuff, trust!!! :

## Balance between readability, scalability and optimizations
- Although having a performant game is nice, a lot of time can be wasted through applying negligible optimizations while also sacrificing both scalability and readibility. Here's an example of micro optimized code vs regular code

  **Scalibility** : "the ability of a computing process to be used or produced in a range of capabilities."*

```lua
local InputService = game:GetService("UserInputService")
local Remotes = game.ReplicatedStorage.Remotes -- not using :GetService() because they're afraid of a function call

if 2 < Variable then -- uses "<" because ">" translates to "<", a very micro optimization

end

-- vs

local InputService = game:GetService("UserInputService")
local Remotes = game:GetService("ReplicatedStorage").Remotes -- staying consistent with the usage of :GetService() above

if Variable > 2 then -- placing the longer expression on the left can improve readability but you lose 1 nanosecond though :CCCCCC

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

    return "ik man"
end
```

- Use conventional and idiomatic methods.

```lua
table.insert(Table, "hi") -- good

Table[#Table + 1] = "hi" -- bad
```

## Comments
- Using comments can help make your code more readable, or the opposite. You'll almost never need to use comments if you're working alone. But if you do, then you should make them as explicit as possible.

*Bad use of comments :*

```lua
-- Variables

local Humanoid = Humanoid -- this is where the humanoid is declared

-- Events

Humanoid.HealthChanged:Connect(function() -- you can use .Died event but for the sake of this example I won't.
    if Humanoid.Health <= 0 then -- checks if player has died
        -- Random comment to make this code harder to reade
    end
end)
```

*Okay use of comments :*

```lua
local Humanoid = Humanoid

Humanoid.HealthChanged:Connect(function() -- does something when the humanoid dies
    if Humanoid.Health <= 0 then
        -- do something
    end
end)
```

## DRY(Don't Repeat Yourself)
- Declare a variable for something that you're using multiple times, use loops and functions for repeated tasks, don't use a hundred scripts and use modules to handle the tasks instead.

 * If you had to handle a group of NPCs, then you should be looping through each npc and handle them accordingly like this :

```lua
local function Attack(Attacker, Target)
    -- do stuff
end

while true do
    for _, Mob in ipairs(List) do
        if WithinRange then
            Attack(Mob, Target)
        end
    end

    wait(1)
end
```

 * Instead of using individual scripts for every NPC like this :

```lua
while true do
    if WithinRange then
        -- do stuff
    end

    wait(1)
end
```

## OOP
- OOP is a programming paradigm, this part assumes you already know what it is so skip it if you don't know what OOP is.

- This programming paradigm is widely misused, remember this is Roblox we're talking about you don't need to make everything(or anything at all) object-oriented.

- OOP is only needed in Roblox when you're working with other scripters to facilitate usage of your co-workers' code. It's useful when making open sourced code as well.

## Simplify your code
- Keep your code simple and tidy, no need to make your code more complex than needed.

## Being stuck
- It's easy to dig yourself in a bottomless pit by taking bad approaches then slapping bandaids constantly and blindly thinking.

- Digging faster in a bottomless pit is useless.

- If you're stuck, open yourself to criticism and feedback.

- Touch some grass will ya?

## Improvement
- If you've written some code, it's a good idea to receive feedback from an outer perspective to further improve it.

- Receiving feedback is great because you can learn something new or discover mishaps.
