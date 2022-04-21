# This is simple example how IntelliJ Editor and Debugger console context works with code autocomplete (suggestions)

### Case 1: not imported module
- Got to file 'hello.js'
- On the line number 3 (after `debugger` line) start to type: `aaa.`
- You will see autosuggestion `iiHasNotBeenImported`
![img.png](img.png)
- You can apply and will not see any error or trying to import it from `test.js`
- The code running will be failed.
- Run debugger, the code will stop on the line 2 (debugger).
- Go to Debugger Console and try to type `aaa.`.
- You will see again `iiHasNotBeenImported`
![img_1.png](img_1.png)

**Questions:** 
- Why `iiHasNotBeenImported` there?
- Why in the editor this suggestion appears if it was not imported? 
- Ok, if it was applied - then it must be imported automatically or IntelliJ must highlight the error, but it is looks fine: 
![img_3.png](img_3.png)
- Why this suggestion appear in the Debugger console during run time if it has not been imported? It will not work anyway!


## Not imported package
- Go to `hello.js`
- Start typing on the last string `aaa.`
- You will same as before (from previous example):
![img_4.png](img_4.png)
- Now install packages:
```shell
yarn install --frozen-lockfile
```
- On the line number 3 (after `debugger` line) start to type: `aaa.`
- You will see autosuggestion from installed package: 
- ![img_5.png](img_5.png)
- Again no errors or automatic import if suggestion was applied:
- ![img_6.png](img_6.png)
- Run `hello.js` in the Debug mode with IntelliJ IDE
- Make sure that code was sopped on the line with 'debugger'
- Got to Debugger console
- Start typing 'aaa.'
- Pay attention on the showed menu with autocompletion suggestions again:
- ![img_7.png](img_7.png)

**Questions:**
- Why suggestions are there?
- Why in the editor this suggestion appears if it was not imported?
- Ok, if it was applied - then it must be imported automatically or IntelliJ must highlight the error, but it is looks fine:
![img_8.png](img_8.png)
- Why this suggestion appear in the Debugger console during run time if it has not been imported? It will not work anyway!

