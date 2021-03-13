# **Handlebars**

- external library
  - collection of prewritten code
  - makes development easier
- templating engine
  - generates reusable HTML with JavaScript
- keeps a clear separation between HTML and JS

--- 
**Boilerplate Code:** code that can be used with little to no modification 
   - not necessary to understand in an in-depth manner 

---

## Adding the Handlebars library to a project

1. Add the library to the project
  - using the CDN:  
  - *Example:*
  ```
  <script src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.0.11/handlebars.js"></script>
  ```
2. Create a Handlebars script in the HTML file
  - delivers a template to the browser
  - *Example:*
  ```
  <script id="ice-cream" type="text/x-handlebars-template">
  ```
3. Grab the HTML stored in the Handlebars script in the JavaScript file
  - double curly braces prompt Handlebars to search for a value to replace the expression
- *Example:*
  ```
  const source = document.getElementById('ice-cream').innerHTML;
  ```
  - use `.getElementById` to access the matching element
  - access the text using `.innerHTML`
  - store in a variable called source
  - pass the source variable into the templating variable as an argument
4. Use `Handlebars.compile()` to return a templating function from the template script
- *Example:*
  ```
  const template = Handlebars.compile(source);
  ```

5. Pass in a `context` object to the templating function to get a compiled template
- *Example:*
  ```
  const context = {
  flavor: 'chocolate'
  };
  ```
- *Example:*
  ```
  const compiledHtml = template(context);
  ```

6. Render the compiled template to the web page
- *Example:*
  ```
  const iceCreamText = document.getElementById('scream');
  iceCreamText.innerHTML = compiledHtml;
  ```

## Using Handlebars Expressions
- Handlebars expressions are wrapped in double braces {{ }} inside a script
- content inside the curly braces serves as a placeholder

- *Example:*  
HTML
 ```
 <script id='greet' type='text/x-handlebars-template'>
    {{greeting}}
    </script>
```
JS 
```
const source = document.getElementById('greet').innerHTML;

const template = Handlebars.compile(source);

const context = {
  greeting: 'Hello Worlds!'
}

const compiledHtml = template(context);

const fill = document.getElementById('hello');

fill.innerHTML = compiledHtml;
```

## `If` block helper
- check for a specific object property before inserting a value
- use the `{{if}}` helper block
  - similar to `if` conditional with different syntax
- has both an opening and closing if expression

```
{{#if argument}}
  // Code to include if the provided argument is truthy 
{{/if}}
```

## `Else` section
- used to add a default line of code in case the if expression evaluates to falsy
- no `#` symbol in front of the `else` keyword

```
{{#if argument}}
  // Code to include if the provided argument is truthy 
{{else}}
  // Code to include if the provided argument is falsy 
{{/if}}
```
`## `Each` and `This``
- iterates through an array
- opening and closing expressions: `{{#each}}` and `{{/each}}`
- `{{this}}` is a placeholder for the array element in the iteration
```
{{#each someArray}}
  <p>{{this}} is the current element!</p>
{{/each}}
```
- `{{this}}` allows access to the properties of the element that is being iterated
```
{{#each someArray}}
  <p>The current shape is: {{this.shape}}!</p>
{{/each}}
```
## Combining `If` and `Each`
- expressions can be combined in a single `<script>`

