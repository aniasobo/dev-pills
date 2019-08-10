# Pure functions vs class methods in JS

Standard module pattern example:  

```
class TransformText {
  constructor(text) {
    this.text = text;
  }

  get text() {
    return this.text;
  }

  capitalize() {
    this.text = this.text.charAt(0).toUpperCase() + this.text.slice(1);
  }

  uppercase() {
    this.text = this.text.toUpperCase();
  }

  lowercase() {
    this.text = this.text.toLowerCase();
  }
}
```

Refactor that allows you to chain those methods:  

```
class TransformText {
  constructor(text) {
    this.text = text;
  }

  get text() {
    return this.text;
  }

  capitalize() {
    this.text = this.text.charAt(0).toUpperCase() + this.text.slice(1);
    return this;
  }

  uppercase() {
    this.text = this.text.toUpperCase();
    return this;
  }

  lowercase() {
    this.text = this.text.toLowerCase();
    return this;
  }
}
```

Chained like this:  

```
let outputText= new TransformText(inputText).uppercase().lowercase().capitalize().text;
```

Functional programming refactor of the above:  

```
// file transformText.js

export const capitalize = (text) => return text.charAt(0).toUpperCase() + text.slice(1);

export const uppercase = (text) => return text.toUpperCase();

export const lowercase = (text) => return text.toLowerCase();
```

👆 Every public method converted to an exported function to be used anywhere.

Benefits of this refactor:  

* **pure** functions: this means they take an input, they don't mutate the input at all, they don't affect anything else in your program at all ("no side effects") and they return an output.
* They have no internal state whatsoever. Nothing is being held in memory after they output their return values.
* The above makes them "idempotent" (expect the same output for the same input every single time") and very predictable.
* They're easy to test and they can be tested in complete isolation

Sample test:  

```
import { uppercase } from './transformText';

describe('uppercase', () => {
  it ('converts a string to uppercase', () => {
    expect(uppercase('some string')).toBe('SOME STRING);
  });
});
```

* use the ES2015 import/export feature so import each of those exported functions where you want to use them