# The diffrence between var const let

### Const and Let

The difference between `var`, `const`, `let`

|   | `var`  | `const` | `let` |
| ------------- | ------------- | ------------- | ------------- |
| Function Scope  | Y  | Y  | Y  |
| Re-assign  | Y  | N  | Y  |
| Re-define/Re-declare  | Y  | N  | N  |

#### Re-define
```es6
let letName = 'a';
let letName = 'a1'; // error re-define `let`
const constName = 'b';
const constName = 'b1'; // error re-define `const`
var varName = 'c';
var varName = 'c1';
```

#### Re-assign

> Re-assign means change the current value to a *new whole value*.


```es6
let letName = 'a';
letName = 'a1';

const constName = 'b';
constName = 'b1'; // error re-assign `const`

var varName = 'c';
varName = 'c1';

const sampleObject = {y:2};
const sampleObject.y = 3; // this is working, {y:3}

sampleObject = {}; // error re-assign change a new whole value
```

#### Function Scope
```es6
function getName()
{
 const constName = 'b';
 console.log("inside", constName);
}
getName();

console.log(varName); // error access, out of `function scope`
console.log(letName); // error access, out of `function scope`
console.log(constName); // error access, out of `function scope`
```
