# ajane
AJANE (Asynchronous Javascript and Nothing Else)

**Ajax** (now superseded by **fetch API**) conventionally retrieves **data** from the server, asynchronously.

But what if you simply want to load and execute **javascript**, asynchronously?

AJANE (Asynchronous Javascript and Nothing Else) is a function which, straightforwardly, enables a `<script>` element which wasn't present when the document was initially loaded to be added to the end of the DOM.
  
## Example:

```
function ajane(scriptName) {

    let allScripts = document.getElementsByTagName('script');
    let lastScript = allScripts[(allScripts.length - 1)];
    
    let newScript = document.createElement('script');
    newScript.classList.add(scriptName);
    newScript.classList.add('ajane');
    newScript.setAttribute('src', '/.assets/design/scripts/' + scriptName + '/scriptName.js');
    
    document.body.insertBefore(newScript, lastScript.nextElementSibling);
}
```
