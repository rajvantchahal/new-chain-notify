## new-chain-notify

Create chaining APIs from functions

## Install

```bash
$ npm install new-chain-notify
```

## Usage

```js
Num(3).sum(10).sub(5).mul(2).val()
// => 16

function Num(x){

    var x = 0
    var chain = newChain(sum, sub, mul) // or: { alias: mul, mul:mul } or: newChain({ alias: mul }, mul)

    chain.val = val

    return chain

    function mul(n){
        x *= n
    }

    function sum(n){
        x += n
    }

    function sub(n){
        x -= n
    }

    function val(n){
        return x
    }

}
```

### `from`

```js
x = [1, 2, 3]

val = newChain.from(x)(foo, bar)

val
// => [1, 2, 3]

val.foo().bar()
// => [1, 2, 3]
```

![](https://dl.dropboxusercontent.com/s/swyw3663x22pnwy/npmel_15.jpg)
