# Mystery Function

What does the `mystery()` function in the following piece of code do? Add your
answer to this markdown file.

TLDR; The mystery function recursively calls itself to slice the first element of the input array until only one element remains.
Each function call will resume and compare the first element of each sliced array. The max value will be returned to mystery.

```javascript
function mystery(a) {						//Function signature
    if(a.length == 1) return a[0];			//If the array has 1 element, return the element
    var foo = mystery(a.slice(1, a.length)) //The function will call itself until it reaches the base case, meaning
											//the array will be sliced until there is one element left.
											//Each function call will pause when it encounters the recursive call.
											//When the base case is reached, each paused call will resume and perform
											//the comparisons to find the array's max value.
    if(foo > a[0]) return foo;				//The first comparison will be with the most recent array after recursively slicing.
											//Foo and a[0] are both equal to the only element in this array, so a[0] will be returned 
											//and foo will remain as a[0]. From this point, each function call that is resumed will
											//add a new element to be compared with foo.
    else return a[0];						//Either foo or a[0] will be returned to mystery (whichever is greater).
}
```

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
