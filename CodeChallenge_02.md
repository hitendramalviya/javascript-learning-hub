
```js
// Array of persons is in hierarchy
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
// Expected output (Array of persons as flat array)
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

# Solution

```js
function convertToFlatArray(nestedObjectArray) {
  const result = [];

  for(let i = 0; i < nestedObjectArray.length; i++) {
    const person = nestedObjectArray[i];
    result.push({ name: person.name, age: person.age });

    if (person.child && person.child.length) {
      console.log('Start of function invocation for child', person.child);
      const childArr = convertToFlatArray(person.child);
      console.log('End of function invocation for child', person.child);
      result.push(...childArr);
    }
  }
  return result;
}
const inputArray = [
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
console.log('Start of program');
console.log(convertToFlatArray(inputArray));
console.log('End of program');
```