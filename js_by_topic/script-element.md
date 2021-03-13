# The `<script>` Element

- introduces interactivity to the HTML skeleton of a webpage
- `<script>` element has an opening and closing angle bracket
  - embed JavaScript code between the opening and closing tags
  - link to external JavaScript files using the `src` attribute to reference the file path name in the opening `<script>` tag
- embeds code similar to the `<style>`  tag in CSS
- if the file is in the same parent folder use a relative path name for the `src` value
- add the script element into the `head` of the HTML file:

```
<head>
    <link rel="stylesheet" href="style.css">
    <!-- Add your script tag here -->
		<script src="./script.js"></script>
</head>
```

## How browsers parse HTML files:
- browsers are equipped with HTML parsers which render the elements in the file
- elements are parsed in the order they appear, from top of the file to the bottom of the file
- a `<script>` element's contents are loaded and executed before the HTML that comes after it
  - delays load time
  - poor user experience
  - as scripts are loaded sequentially, scripts should be loaded after any script they depend upon  

## Defer attribute:
  - specifies a script should be executed only after the HTML file is completely parsed
  - script is loaded but execution is deferred
  - useful when a script's funtionality requires interaction with the DOM
    - ensures the entire HTML file is parsed before the script is executed

*Example:* `defer`

`<script src="example.js" defer></script>`

## Async attribute:
  - specifies a script to load and execute asynchronously with the rest of the HTML
    - remaining HTML is parsed as the script is downloaded in the background
  - unlike `defer`, an `async` script will execute immediately after it has downloaded
  - useful for scripts that run independently of other scripts
  - optimizes web page load time

  *Example:* `async`

`<script src="example.js" async></script>`