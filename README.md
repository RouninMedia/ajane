# ajane
AJANE (Asynchronous Javascript and Nothing Else)

**Ajax** (and its contemporary successor, **fetch API**) conventionally retrieves **data** from the server, asynchronously.

But what if you simply want to load and execute **javascript**, asynchronously?

AJANE (Asynchronous Javascript and Nothing Else) is a function which, straightforwardly, enables a new `<script>` element (which wasn't present when the document was initially loaded) to be added to the end of the DOM.

After the new `<script>` element is added, the browser will automatically load and execute the script it references.
  
## Example:

```
function ajane(scriptName) {
    
    let newScript = document.createElement('script');
    newScript.classList.add(scriptName);
    newScript.setAttribute('src', `/.assets/design/scripts/${scriptName}/${scriptName}.js`);
    
    document.body.appendChild(newScript);
}
```
