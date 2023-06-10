# Summer_PEP_2023
1. If the given input is an array of numbers, return the sum of all the positive ones. If the array is empty or there aren't any positive numbers, return 0.
const input = [1, -4, 12, 0, -3, 29, -150];

Answer: 

const input = [1, -4, 12, 0, -3, 29, -150];

const sumPositiveNumbers = (arr) => {

    let sum = 0;
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > 0) {
            sum += arr[i];
        }
    }
    return sum;
}

console.log(sumPositiveNumbers(input));

//Output
42

2. Square the value of every element in the array. Presume that you will only get numbers in the input array.
const input = [1, 2, 3, 4, 5];

Answer:

const input = [1, 2, 3, 4, 5];

const squareArray = (arr) => {

    let result = [];
    for (let i = 0; i < arr.length; i++) {
        result.push(arr[i] * arr[i]);
    }
    return result;
}

console.log(squareArray(input)); 
//Output
[ 1, 4, 9, 16, 25 ]

3. Calculate the mean and median values of the number elements from the input array.
const input = [12, 46, 32, 64];

Sol -> 
const input = [12, 46, 32, 64];

var meanMedian = (arr) => {

    let mean = 0;
    let median = 0;

    let sum = 0;
    for(var i=0;i<arr.length;i++){
      sum += arr[i];
    }

    mean = sum/arr.length;
    console.log(mean);
    //Since length of arr is even so median will be sum of two middle elements divided by 2.
    median = (arr[1] + arr[2])/2;
    console.log(median);
  
}

 meanMedian(input);

Output: 
mean = 38.5
median = 39

4.Find the difference in age between the oldest and youngest family members, and return their respective ages and the age difference.


const input = [

 {
   name: "John",
   age: 13,
 },
 {
   name: "Mark",
   age: 56,
 },
 {
   name: "Rachel",
   age: 45,
 },
 {
   name: "Nate",
   age: 67,
 },
 {
   name: "Jennifer",
   age: 65,
 },
];



Answer: 
const ageDifference = (arr) => {

    let minAge = arr[0].age;
    let maxAge = arr[0].age;
    for (let i = 1; i < arr.length; i++) {
        if (arr[i].age < minAge) {
            minAge = arr[i].age;
        }
        if (arr[i].age > maxAge) {
            maxAge = arr[i].age;
        }
    }
    return {oldest: maxAge, youngest: minAge, difference: maxAge - minAge};
}

console.log(ageDifference(input));

 Output:
 { oldest: 67, youngest: 13, difference: 54 }

5. If the given input is a number, you should return the factorial of that number. The factorial of a natural number n is the product of the positive integers less than or equal to n. So, 2! = 2, 3! = 6, 4! = 24 and so on.


Answer: 
const factorial = (n) => {

    let result = 1;
    for (let i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

console.log(factorial(2)); // Output: 2
console.log(factorial(3)); // Output: 6
console.log(factorial(4)); // Output: 24


6. You are given an array of objects representing a collection of products, each with a name, price, and category. Your task is to use find the average price of products in each category, and then return an array of objects containing only the categories that have an average price above 50.


const products = [

 { name: "Product 1", price: 20, category: "Electronics" },
 { name: "Product 2", price: 30, category: "Clothes" },
 { name: "Product 3", price: 40, category: "Electronics" },
 { name: "Product 4", price: 50, category: "Clothes" },
 { name: "Product 5", price: 60, category: "Clothes" },
 { name: "Product 6", price: 70, category: "Electronics" },
 { name: "Product 7", price: 80, category: "Clothes" },
 { name: "Product 8", price: 90, category: "Electronics" },
];

Sol -> 
function calculateAveragePriceByCategory(products) {

  const categorySumCountMap = {};
  
  for (let i = 0; i < products.length; i++) {
  
    const product = products[i];
    
    if (categorySumCountMap.hasOwnProperty(product.category)) {
      categorySumCountMap[product.category].sum += product.price;
      categorySumCountMap[product.category].count++;
    } else {
      categorySumCountMap[product.category] = {
        sum: product.price,
        count: 1
      };
    }
  }
  
 const categoryAverages = [];
  
 for (const category in categorySumCountMap) {
  
    const sum = categorySumCountMap[category].sum;
    const count = categorySumCountMap[category].count;
    const average = sum / count;
    
    if (average > 50) {
      categoryAverages.push({
        category: category,
        averagePrice: average
      });
    }
  }
  
    return categoryAverages;
}

const products = [

  { name: "Product 1", price: 20, category: "Electronics" },
  { name: "Product 2", price: 30, category: "Clothes" },
  { name: "Product 3", price: 40, category: "Electronics" },
  { name: "Product 4", price: 50, category: "Clothes" },
  { name: "Product 5", price: 60, category: "Clothes" },
  { name: "Product 6", price: 70, category: "Electronics" },
  { name: "Product 7", price: 80, category: "Clothes" },
  { name: "Product 8", price: 90, category: "Electronics" },
];

const result = calculateAveragePriceByCategory(products);
console.log(result);


Output: [

  { category: "Electronics", averagePrice: 55 },
  { category: "Clothes", averagePrice: 55 }
  
]
