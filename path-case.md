As we know, mac's filesystem(HFS+) is not case sensitive while unix-like os or Windows's does. And it could cause some trouble thing when u defined a file and a directory with same name but different case under a folder.
E.G.:
```
/folder
  /testcase
    index.js
  testCase.js
```
The case showed above is that we will require testCase.js in our js. And the main conferrence in package.json is default
 which is 'index.js'. Then we can require it as:
```
const testCase = require('./folder/testCase');

testCase(); // assume both file export a function print content 'This is index.js' or 'This is testCase.js'
```
Then the result is 'This is testCase.js', because node will require file first. Once u delete the testCase.js, then the
result will be different. 'This is index.js' is printed. So, remember, don't just put file and directory with same name in same folder, nonetheless, u will get into hot water.
