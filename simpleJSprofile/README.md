# simpleJSprofile.js
Lightweight javascript library with no external JS dependencies that profiles time taken by a function. Used by web developers who want a quick glance at how quickly their javascript function runs. Tested with Firefox 52, IE11 and Chrome 58.

Makes use of the performance API if the browser is compatible otherwise uses simple system clock API. Unlike Date.now(), the values returned by Performance.now() always increase at a constant rate, independent of the system clock

For advanced benchmarking I would recommend the jsperf or Benchmark.js libraries.

## Window.Performance Documentation: 

https://developer.mozilla.org/en-US/docs/Web/API/Performance

https://developer.mozilla.org/en-US/docs/Web/API/Performance/now

## Linking  Include simpleJSprofile.js in the page you want to profile: 
<script src="simpleJSprofile.js"></script>

## Example Usage  
ms=getRunMilliseconds(functionName);   

console.log(ms); //console output milliseconds elapsed "2001.0002"

//add any parameters to functionName in second parameter as an array 

printRunMilliseconds(functionName,['Hello ','World!']); //console output "Elapsed: 2001.0002 ms". 

## Using Multiple Stopwatches  

//Start 1st Stopwatch 

var stopwatch1 = new StopWatch(); 

//Do some work  

//console output time 

stopwatch1.printElapsedMilliseconds();  

//Start 2nd Stopwatch - variables are object specific so multiple StopWatches work with min space 

var stopwatch2 = new StopWatch(); 

//Do some more work  

//Optionally you can stop both stopwatches for a more accurate reading 

stopwatch1.stop(); 

stopwatch2.stop(); 

//console output time 

stopwatch1.printElapsedMilliseconds();  

stopwatch2.printElapsedMilliseconds();    

## Formatting Output
stopwatch.printElapsed(type,floor);

type=[ms, sec, min, hrs] //set output to milliseconds, seconds, minutes, or hours respectively 

floor=[false, true] //whether or round return value to previous integer 
