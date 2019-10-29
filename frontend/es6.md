# Es6 cheatsheat
credit : https://github.com/DrkSephy/es6-cheatsheet

### html module script
```html
<script type="module">
import * from "./src/somewhere"
</script>
```

### export
```
export let name = 'David';
export let age  = 25;​​
```
```
function sumTwo(a, b) {
    return a + b;
}

function sumThree(a, b, c) {
    return a + b + c;
}

export { sumTwo, sumThree };
```
```
export function sumTwo(a, b) {
    return a + b;
}

export function sumThree(a, b, c) {
    return a + b + c;
}
```
```
function sumTwo(a, b) {
    return a + b;
}

function sumThree(a, b, c) {
    return a + b + c;
}

let api = {
    sumTwo,
    sumThree
};

export default api;
```

### import
```
import 'underscore';
import { sumTwo, sumThree } from 'math/addition';
import {
    sumTwo as addTwoNumbers,
    sumThree as sumThreeNumbers
} from 'math/addition';
import * as util from 'math/addition';
import * as additionUtil from 'math/addition';
const { sumTwo, sumThree } = additionUtil;
import api from 'math/addition';
```

