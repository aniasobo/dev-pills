# Jasmine

### Without SpecRunner.html

1. add jasmine to your package.json:

```
"devDependencies": {
    "jasmine": "^3.2.0"
  },
"dependencies": {
    "jasmine-node": "^3.0.0"
  }
```

specify command to run your tests:

```
  "scripts": {
    "test": "jasmine"
  },
```

2. `npm install`
2. in your project directory: `npm install -g jasmine`
3. write your tests
4. in command line: `jasmine` to run the tests

in detail: `node_modules/jasmine-node/bin/jasmine-node --verbose --junitreport --noColor spec`

### With SpecRunner.html

Follow the [Jasmine getting started documentation](https://jasmine.github.io/pages/getting_started.html)

1. add Jasmine to your project
2. replace the scripts in `SpecRunner.html` with your own
3. to run tests, open the SpecRunner in your browser