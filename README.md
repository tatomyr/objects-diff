# object-diff
This script provides function that substract second Object from first. E.g. 
```
const x = { 
  a: 1, 
  b: 2 
}, y = { 
  a: 1 
};

x.diff(y); // => { b: 2 }
y.diff(x); // => {}
```
You can add the script by adding further tag to your page:
```
<script src="https://tatomyr.github.io/objects-diff/diff.js"></script>
```
or in console:
```
const script = document.createElement('script');
script.src = 'https://tatomyr.github.io/objects-diff/diff.js';
document.body.appendChild(script);
```
## Test page
You can test how it works at <a href="https://tatomyr.github.io/objects-diff/">test page</a>

###### More example of objects to test:
```
const x = {
  a: 1,
  b: { 
	bA: 11, 
	bB: 22, 
	bC: { v: 'alpha', w: 'beta', '*': 'gamma', '#': 'dalet' } 
  },
  c: 'just c',
  d: ['o', 'v', 'w', '*', '#'],
  e: { q: 'Q', w:'W',e:'E',r:{r1:1,r2:2} }
}, y = {
  a: 1,
  b: { 
	bA: 11, 
	bB: 22, 
	bC: { v: 'alpha', w: 'beta', '*': 'gamma', '#': 'delta' } 
  },
  c: { 
    cA: 33, 
    cB: { cBa: 444, cBb: 555 } 
  },
  d: ['o', 'v', 'w', '*', '~', '#'],
  e: { q: 'Q', w:'W',r:{r1:1,r2:2},e:'E' }
};

x.diff(y); // => { b: { bC: { '#': 'dalet' } }, c: 'just c', d: { 4: '#' } }
y.diff(x); // => { b: { bC: { '#': 'delta' } }, c: [Object], d: { 4: '~', 5: '#' } }
```
