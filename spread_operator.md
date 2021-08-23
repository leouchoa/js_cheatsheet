This is example is extracted from [here](https://slides.com/bgando/f2f-final-day-1#/7/14).

Let's take a look at the next function. Notice that accepts 4 parameters and returns a new data structure from them. 

```
const createTuple = function(a, b, c, d) {
  console.log(arguments);
    //['It', 'be', 'could', 'anyone', 'no one']
  return [[a, c],[ b, d]];
}
```

But what if we call it with 5 parameters instead? It should output an error right? Well not really... It actually just ignores the last one.

```
>> createTuple('It', 'be', 'could', 'anyone', 'no one'); 

Array [ (2) […], (2) […] ]
0: Array [ "a", "c" ]
1: Array [ "b", "d" ]
length: 2
<prototype>: Array []
```

But if you want to also capture the last, because you don't know how many parameters will given in advance, you can use the spread operator.

```
const createTuple = function(a, b, c, ...d) {
  console.log(arguments);
    //['It', 'be', 'could', 'anyone', 'no one']
  return [[a, c],[ b, d]];
}

createTuple('It', 'be', 'could', 'anyone', 'no one'); 
```
The spread operator will gather the fourth and beyond arguments passed into an array so you can capture as many arguments as possible.
