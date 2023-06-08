
```js
// Array of person
const arr = [
  {
    name: "Test",
    age: 40,
    child: [
      {
        name: "Test.0",
        age: 22,
        child: [
          {
            name: "Test.0.0",
            age: 4,
          },
        ],
      },
    ],
  },
];
// Expected output
const persons = [
  {
    name: "Test",
    age: 40,
  },
  {
    name: "Test.0",
    age: 22,
  },
  {
    name: "Test.0.0",
    age: 4,
  },
];

// Problem statement, write a function to produce flat array from a deep nested array, input array is given above & expected result also shown in above code snippet.  
```