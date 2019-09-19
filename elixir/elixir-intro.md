# Elixir intro notes

Extension: `.ex` & `.exs`  

Compile & run with `$ mix`  

## Installation

* installs with Erlang
* installs with an interactive shell called `IeX`
* installs with `Mix`, a build tool for creating, compiling, testing, managing dependencies etc
* installs with a package manager called `Hex`

## `IeX`

`$ iex` - `$ C^`

to run your project in the shell, from within the root dir: `$ iex -S mix`  

to use functions: `$ MyProj.method` or `$ MyProj.method()`  

Recompile inside the shell with `$ r MyProject`  

## `Mix`

* scaffold a new Elixir project with `$ mix new my_project`  
* `mix.exs` is the config of the project generated 
* also generated: `lib/` directory with `my_project.ex` and `test/` directory with generated test helper and test for the lib file

**`$ mix test` to run your tests inside the project directory**  



## `Enum.`

`$ Enum.` + tab to see all available `Enum` commands  

**`Fetch` and `at`**  

`$ Enum.fetch(item, int)` returns a tuple with status  

`$ Enum.at(item, int)` returns item at given index  

**`Map`**  

`$ Enum.map([1, 2, 3], fn(x) -> x * 2 end)` returns `[2, 4, 6]`    

functions are written inline - convention  

**`concat`**  

`$ Enum.concat([1,2,3],[2,3,4])` returns `[1, 2, 3, 2, 3, 4]`  

**`Enum.max`**  

`$ Enum.max([1,2,3])` will return the highest value on the list

## Other methods 

`$ h (Enum)` - `h()` is an Elixir helper method that explores a given entity (not really similar to pressing `<tab>`, as it's more narrative)  

---

## Variable assignment

**Immutability**  

Variables can't be reassigned; can be manipulated like so:  

`$ my_list = [1, 2, 3]`  

`$ my_list = my_list ++ [4]`  

This can be prevented with `$ ^my_list = [1,2,3]` (pinning; does not seem to make a difference in `iex`)  

---

## Atoms

A constant used for naming; denoted by a colon (like symbols in Ruby): `:my_atom`.  

Instantiate: `$ my_atom = :my_atom` (these become interchangeable)  


