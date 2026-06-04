**NOTE:** this doesnt work in windows because windows has no `AF_UNIX` socket and this is like the ony reliable way to do IPC

Which repo do you want to go to?
================================

-   **[libimportx](https://github.com/itzmetanjim/libimportx)**: The spec itself
-   **[libimportx-js](https://github.com/itzmetanjim/libimportx-js)**: Javascript implementation\
    [npm](https://www.npmjs.com/package/libimportx) `npm install libimportx`
-   **[libimportx-python](https://github.com/itzmetanjim/libimportx-python)**: The Python implementation\
    [PyPI](https://pypi.org/project/libimportx/) `pip install libimportx`

If you cloned this repo, the source code for all 3 of these are in submodules.

How to use
==========

Python
------

```python
from libimportx import*

# To import a file
mymodule=importx("file.js")
mymodule.whatever_function_you_want("args")

# To export this file
exportx() # NoReturn if importx'ed, otherwise returns False
# Otherwise it falls here
print("Standalone")
```

JS
--

```js
var {importx,exportx}=require("libimportx")
// To import a file
var mymodule=await importx("file.py") //IMPORTANT!! in js you need await
await mymodule.myfunction() //you need await
await mymodule.var
mymodule.var="value" //no await here
// To export this file
var mystuff=(a)=>{console.log(a)} //defined something to export
module.exports={mystuff} //classic js stuff
if (!exportx()){ //does NOT block, returns whether it was importx'ed or not
console.log("Standalone")
}
```




(why i had to make this: flavortown shipwright does not want repo link to be an HTML file)
