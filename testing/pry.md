# Pry

(raw notes from usage in Ruby and Rails projects)

**Exit pry with `!!!`**

* add to gem file, bundle etc
* it's like irb for the spec
* add `binding.pry` to spec file inside the it block where you want to pick up (stuff before will be executed like in irb with require but without the full file)
* add the require in the `spec_helper` - `require 'pry'`
* rspec -fd (?? opens pry?)
* `exit!` to exit pry
* `.rspec` autogenerated file has the `require "spec_helper"` so you don't have to require it in your spec files (unless you don't have it in your project)
* `save_and_open_page` and `$ puts page.body` let you peek inside the DOM from the POV of the Selenium Driver (in command line within pry)
* target invisible elements while in pry
