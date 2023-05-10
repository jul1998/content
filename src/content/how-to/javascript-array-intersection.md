# Javascript Array Intersection

As a developer, you're often faced with the challenge of comparing arrays to find common elements and perform a specific logic. Array intersection, the process of determining overlapping values in different arrays, can help you create a new array holding only common and non-duplicated elements. In the following article, we'll see many approaches to understand array intersecion usin JavaScript.

In the following coding snippet, you will see a quick example of how this works:


```js

    let array1 =  [1, 2,3, 4 ,5]

    let array2 =  [3, 4,5, 6, 7]


    const filteredArray = array1.filter(value => 
    array2.includes(value));


        // Output: [3, 4, 5]
   
 ```

## Get the intersection of multiple arrays using filter()


The previous code example shows the filter method in JavaScript that allows the composition of a new array that holds the common elements in two or more arrays based on the criteria specified in the method in question.

Using a similar syntax, you can also check for the difference between arrays to know the elements that are not in myArr1 and myArr2:

 ```js
    let difference = myArr1.filter(x => !myArr2.includes(x));


    //Output:
    //difference = [1,2]
```

## Get the intersection of multiple arrays using a for loop

This time, we use a for loop to iterate over an array to implement an array intersection to obtain every element in the first array. Then, it uses another method called 'includes()' to verify if each element in the first array is included in second one.

```js
    let myArr1 = [1,2,3 ,4 ,5]
    let myArr2 = [3,4, 5,6 ,7]


    //We create  new array to store new numbers


    let new_arr =  []

    for(i = 0; i < myArr1.length; i++) {

            if  (myArr2.includes(myArr1[i])) {

                  new_arr.push(myArr1[i])
            }
    }
        //Output:
        //  intersection = [3,4,5]
    
   ```

In addition, another way of using a for loop to get the same exact  result but without using the 'includes()' technique is utilizing a nested for loop.

```js
        let myArr1 =  [1,2, 3, 4,5 ]
        let myArr2 =  [3,4,5 ,6 ,7]

    //Again, we create  new array to store new numbers

        const result = [];


    for (let  i = 0; i < myArr1.length; i++) {
            
        for (let  j = 0; j < myArr2.length; j++){

                if (myArr1[i]  === myArr2[j] ) {
                        result.push(myArr1[i]);
                            break;
                }

            }
        }


        //Output:
        // [3,4,5]
    
    
```
## Get the intersection of multiple arrays using the Set object

Set objects are collections that do not allow duplicated elements to be stored, hence each element inside will be unique. In this form it is possible to  identify the array intersection by removing duplicates. 

```js
    let myArr1 =  [1,2, 3,4,5]

    let myArr2 =  [3,4, 5,6, 7]

    const set1 = new Set(myArr1);
    const set2 = new Set(myArr2);


    let intersection = [...set1].filter(element =>      set2.has(element));


        //Output:
        //   [3, 4, 5]
```
## Real-world example using the intersection of multiple arrays

Imagine that you are developing a website that will offer a search bar as a component for your visitors to find products easily by typing the name. Your objective is to implement an autocomplete feature that suggests search terms to users based on the keywords that have been looked up by other users in the past while navigating that website. So, how can you use arrays intersection to get this goal?

First, you can store various words that users have looked up in the past.
 ```js
    //Create an array to store search terms
    let searchedKW = ['iphone', 'ipad', 'macbook' 'ipod', 'imac', 'apple','watch', 'alexa', 'xiaomi', 'phillps'];
```
Then,  take the input typed by the user in the search bar.
 ```js
    //Store user input in a variable
    let userInput = "IP"
```
Having both the array with all the values and the user input, you can apply an array intersection to autocomplete what the user is typing.
```js
    let filteredKW = searchedKW.filter
    
    (searchterm => searchterm.toLowerCase(). 
startsWith(
    userInput.toLowerCase()
    )
);
        //output
        //  [ "iphone",  "ipad", "ipod", "imac" ]
```
Lastly, the user  (or you) will have the chance to see this autocomplete feature in action which will improve their user experience significantly... All of this is due to this great JavaScript approach that can be easily implemented when needed.

## Conclusion

In conclusion, you could see numerous methods to find the intersection between two or more arrays using filter(), includes(), for loops, and Set objects. Rest assured this knowledge will help you at some point in your developer journey when working with data structures and you can revisit this article as many times as you need to review each explanation and example.
