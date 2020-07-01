# Array-Iteration-Methods
```js
/*============================================= = Start of .forEach() method ==============================================*/

        const names = ['Selma', 'Ted', 'Mike', 'Sam', 'Sharon', 'Marvin'];

        let sNames = [];

        names.forEach(name => {
            if (name.charAt(0) === 'S') {
                sNames.push(name);
            }
        });

        console.log(sNames);

        //const fruits = ['apple', 'pear', 'cherry'];
        /*
        for(let i = 0; i < fruits.length; i += 1) {
          console.log(fruits[i]);
        }
        */

        //one line makes it much easier as u dont need to increment, it wont be endless n itll break itself without bugs.
        //Though it doesnt let u break out of theloop in between then u better just use for or while loop if u need to break out of the loop at certain point


        /*
        fruits.forEach(fruit => (fruit) );
        */

        /*
        //THis way is eassier than for loop to loop through the whole array but one line is still easier n right now this is all done through a callback arrow function
        fruits.forEach( fruit => { 
          console.log(fruit);
        }); 
        */
        const fruits = ['apple', 'pear', 'cherry'];

        let capitalizedFruits = [];

        fruits.forEach(fruit => {
            let capitalizedFruit = fruit.toUpperCase();
            capitalizedFruits.push(capitalizedFruit);

        });
        console.log(capitalizedFruits);



        const prices = [6.75, 3.10, 4.00, 8.12];
        let total = 0;
        // Total: 21.97

        prices.forEach(price => {
            total += price; // += is not good if you use old JS code beter just a + operator even longer code

        });
        console.log(total);

        //Another exercise iterating through
        const names = ['Selma', 'Ted', 'Mike', 'Sam', 'Sharon', 'Marvin'];
        let sNames = [];
        // Result: ['Selma', 'Sam', 'Sharon'];

        names.forEach(name => {
            if (name.charAt(0) === "S") {
                sNames.push(name);
            }
        });
        console.log(sNames);


        //Using forEach, iterate over the numbers array and multiply each number by 10, storing these new numbers in the times10 array.
        //Another Example
        const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
        let times10 = [];
        numbers.forEach(function(number) {
            times10.push(number * 10);
        });
        // times10 should be: [10,20,30,40,50,60,70,80,90,100]
        // Write your code below



        //Using forEach, copy only the first 2 characters of each string in the days array and store the abbreviations in the dayAbbreviations array.

        const days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
        let dayAbbreviations = [];

        // dayAbbreviations should be: ['Su', 'Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa']
        // Write your code below

        days.forEach(day => {
            const dayAbbreviation = day.slice(0, 2);
            dayAbbreviations.push(dayAbbreviation);
        });






        /*============================================= = Start of .map() method ==============================================*/
        // Working with JSON Objects in an Arrray especially accessign JSON that's stored in an Array with .map special method
        const users = [{
            name: 'Samir',
            age: 27
        }, {
            name: 'Angela'
        }, {
            name: 'Beatrice'
        }];


        const newUsersArray = users.map(user => `${user.name} is  ${user.age}  years old`);
        console.log(newUsersArray);




        //************* HERE  WE'RE GOING TO TRANSFORM ARRAY ITEMS WITH .map() Method

        // Another example with ratex which is usually 10
        const strings = ['1', '2', '3', '4', '5'];

        // after string the number 10 is a ratex which usually should be 10
        const numbers = strings.map(string => parseInt(string, 10));
        console.log(numbers);


        const fruits = ['apple', 'pear', 'cherry'];
        /*
        let capitalizedFruits = [];
        fruits.forEach(fruit => {
          let capitalizedFruit = fruit.toUpperCase();
          capitalizedFruits.push(capitalizedFruit);
        });
        */

        const capitalizedFruits = fruits.map(fruit => fruit.toUpperCase());
        console.log(capitalizedFruits);





        // Another example with prices
        const prices = [5, 4.23, 6.4, 8.09, 3.20];

        // Result: [ '$5.00', '$4.23', '$6.40', '$8.09', '$3.20' ]


        //So it returns it as a two digit number result with the $ sign through string interpolation
        const pricing = prices.map(price => `$${price.toFixed(2) }`);







        /*============================================== Start of .filter() method ==============================================*/

        //const names = ['Selma', 'Ted', 'Mike', 'Sam', 'Sharon', 'Marvin'];

        //let sNames = [];
        /*
        names.forEach(name => {
          if(name.charAt(0) === 'S') {
            sNames.push(name);
          }
        });
        console.log(sNames);
        */
        // The same what we did with .forEach now trying to do with filter method

        const sNames = names.filter(name => name.charAt(0) === 'S');
        console.log(sNames);

        //Another way of doing this
        const startsWithS = name => name.charAt(0) === 'S';
        const sNames = names.filter(startsWithS);
        console.log(sNames);

        // This is how we return everything beside 3
        const numbers = [1, 2, 3, 4, 5];
        const no3 = numbers.filter(number => number !== 3);

        //However, if we want only one number 2 let's say
        const no3 = numbers.filter(number => number === 2);
        console.log(no3);

        //Returning even numbers with dividing into 2 and equals 0 Finding the odd or even number with Powerful filter method
        const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
        const evens = numbers.filter(number => number % 2 === 0);
        console.log(evens);




        /*============================================== Start of .reduce() method ==============================================*/

        /* The reducer function takes four arguments:
         * 1)Accumulator (acc)
         * 2)Current Value (cur)
         * 3)Current Index (idx)
         * 4)Source Array (src)
         */
        // Use the reduce method to return a single value from an array of values
        /*
        const prices = [6.75, 3.10, 4.00, 8.12]; // Total: 21.97
        let total = 0;
        prices.forEach(price => {
            total += price;
        });
        console.log(total);
        */
        let total = [0, 1, 2, 3].reduce(
            (acc, cur) => acc + cur,
            0

        );
        console.log(total);

        // sum is the Accumulator and the price si the Current Value argument
        // And the initial value for the Accumulator sum is set to 0
        const total = prices.reduce((sum, price) => sum + price, 0);

        console.log(total);



        const names = ['Gary', 'Pasan', 'Gabe', 'Treasure', 'Gengis', 'Gladys', 'Tony'];

        const gnameCount = names.reduce((count, name) => {

            if (name[0] === "G") {
                return count + 1;
            }
            return count;
        }, 0);
        console.log(gnameCount);
        // So it returns number 4 as there are only 4 items starting with G letter. Also we could use charAt(0)


        const phoneNumbers = ["(503) 123-4567", "(646) 123-4567", "(503) 987-6543", "(503) 234-5678", "(212) 123-4567", "(416) 123-4567"];
        let numberOf503;

        // numberOf503 should be: 3
        // Cuz the substring counts the first n last bracket as first fifth item so we're doing .substring(0,5)
        numberOf503 = phoneNumbers.reduce((count, number) => {

            if (number.susbtring(0, 5) === "(503)") {
                return count + 1;
            }
            return count;
        }, 0);




        /*============================================== Start of Chaining Array Methods ==============================================*/


        const arr = [1, 2, 3];

        const smallerArr = arr.filter(number => number !== 2);
        const incrementedArr = smallerArr.map(number => number + 1);

        console.log(incrementedArr); // => [2,4]

        // And then we could do like

        const smallerArr = arr
            .filter(number => number !== 2)
            .map(number => number + 1);


        // Another example 

        const years = [1989, 2015, 2000, 1999, 2013, 1973, 2012];
        let displayYears;

        // displayYears should be: ["2015 A.D.", "2013 A.D.", "2012 A.D."]
        displayYears = years.filter(year => year > 2000)
            .map(year => `${year} A.D.`);



        /*
        Removing Duplicates from an Array
To remove duplicate elements from an array, we can use filter(). Remember, the filter method provides three parameters to our callback function: the current element being processed in the array, the index of the current element being processed in the array, and the array filter() was called upon.
We can compare the index of the current element to the index of the current element in the array that filter() was called upon to determine if we've already encountered that element value. This works because the indexOf method will return the index of the first occurrence that is found in the array. So, indexes of duplicate elements will not equal the index of the first occurrence of their values.
*/
        const numbers = [1, 1, 2, 3, 4, 3, 5, 5, 6, 7, 3, 8, 9, 10];

        const unique = numbers.filter(function(number, index, array) {
            return index === array.indexOf(number);
        });

        console.log(unique); // => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]




        /*============================================== Start of Working with Objects in Arrays ==============================================*/

        const users = [{
            name: 'Samir',
            age: 25
        }, {
            name: 'Angela',
            age: 26
        }, {
            name: 'Beatrice',
            age: 42
        }];

        const ageOfUsers = users.map(user => `${user.name} is ${user.age} years old`);



        const newUsersArray = users.filter(user => user.name != 'Samir');
        console.log(newUsersArray);


        // creatinga seperate object from the object which we have in the array
        const newObject = users.reduce((usersObject, user) => {

            usersObject[user.name] = user.age;
            // always remember to return a value in the callback function
            return usersObject;

        }, {});

        /* Using the map method on the authors array, create an array of full name strings, comprising the first name, then a space, then the last name. 
        See the comments below for reference. Store the new array in the fullAuthorNames variable. */

        const authors = [{
            firstName: "Beatrix",
            lastName: "Potter"
        }, {
            firstName: "Ann",
            lastName: "Martin"
        }, {
            firstName: "Beverly",
            lastName: "Cleary"
        }, {
            firstName: "Roald",
            lastName: "Dahl"
        }, {
            firstName: "Lewis",
            lastName: "Carroll"
        }];
        let fullAuthorNames;

        // fullAuthorNames should be: ["Beatrix Potter", "Ann Martin", "Beverly Cleary", "Roald Dahl", "Lewis Carroll"]
        // Write your code below
        fullAuthorNames = authors.map(author => `${author.firstName} ${author.lastName}`);
        console.log(fullAuthorNames);



        const userNames = ['Samir', 'Angela', 'Beatrice', 'Shaniqua', 'Marvin', 'Sean'];

        // Result: [{name: 'Samir'}, {name: 'Shaniqua'}, {name:'Sean'}];


        const usersTemp = userNames
            .filter(name => name.charAt(0) === "S")
            .map(name => ({
                name
            }));


        const users = [{
            name: 'Samir',
            age: 27
        }, {
            name: 'Angela',
            age: 33
        }, {
            name: 'Beatrice',
            age: 42
        }, {
            name: 'Shaniqua',
            age: 30
        }, {
            name: 'Marvin',
            age: 23
        }, {
            name: 'Sean',
            age: 47
        }];


        const userNames = users.filter(user => user.age >= 30).map(user => user.name);

        // Result: ['Angela', 'Beatrice', 'Shaniqua', 'Sean'];



        // IF there's unfinished task select those and print the name of the task that's unfinished

        const todos = [{
            todo: 'Buy apples',
            done: false
        }, {
            todo: 'Wash car',
            done: true
        }, {
            todo: 'Write web app',
            done: false
        }, {
            todo: 'Read MDN page on JavaScript arrays',
            done: true
        }, {
            todo: 'Call mom',
            done: false
        }];
        let unfinishedTasks;

        // unfinishedTasks should be: ["Buy apples", "Write web app", "Call mom"]
        // Write your code below
        unfinishedTasks = todos.filter(task => task.done === false).map(task => task.todo);
        ```
