# JavaScript recursive functions

### Recursive functions

**Recursive functions** can call themselves:

```javascript
function recursiveFunction() {    
    // assume playSound(file) is defined 
    playSound('ding.wav')
    recursiveFunction()
}

recursiveFunction()
```

We can easily see that this would result in an endless loop - like a dog chasing its tail!

### Exit conditions

So, to work like a (sane) normal function, a recursive function must have an **exit condition**:

```javascript
function recursiveFunction() {
    // assume minuteNow and secondNow come from a clock
    // assume playSound(file) is defined 
    playSound('ding.wav')
    if (minuteNow > 0 && secondNow > 0) {
        recursiveFunction()
    }    
}    

recursiveFunction()
```

The exit condition in the above is the silent `else` branch which lets the function not call itself again :)
