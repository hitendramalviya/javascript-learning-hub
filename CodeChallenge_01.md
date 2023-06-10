# Code challenge 1

Create a JavaScript program that calculates the average score of a student's grades.

Requirements:
1. The program should prompt the user to enter the number of grades they want to calculate the average for.
2. The program should then prompt the user to enter each grade one by one.
3. After all the grades are entered, the program should calculate the average score.
4. The average score should be displayed to the user.

Example Output:
```yaml
How many grades do you want to calculate the average for? 4
Enter grade 1: 85
Enter grade 2: 90
Enter grade 3: 77
Enter grade 4: 92
The average score is: 86
```

Here are some guidelines for mentees to follow when completing the assessment:
- Use variables and appropriate data types to store the user input and calculate the average.
- Utilize loops to prompt the user for each grade.
- Implement proper error handling to handle invalid input.
- Break the problem down into smaller steps and use functions if needed.
- Pay attention to code organization, readability, and comments.

# Solution

```js
// let totalNoOfUsers;
// let sumOfGrades = 0;
// for (totalNoOfUsers = 1; totalNoOfUsers <= 5; totalNoOfUsers++) {
//     const input = parseInt(prompt());
//     console.log(`Enter grade ${totalNoOfUsers}: ${input}`);
//     sumOfGrades += input;
// }
// const avrageOfGrades = sumOfGrades/5;
// console.log(avrageOfGrades);

function isValidInput(input) {
  const isValid = typeof input === 'number' && !Number.isNaN(input) && input > 0 && input <= 100;

  if (!isValid) {
    alert('Invalid input, please provide a valid positive integer value between 0 & 100!');
    return false;
  }

  return true;
}

// 1. The program should prompt the user to enter the number of grades they want to calculate the average for.
function getNumberOfUsers() {
  const totalNoOfUsers = prompt('Total no of users');
  const convertedNoOfUsers = parseInt(totalNoOfUsers); // A valid number or NaN

  if (!isValidInput(convertedNoOfUsers)) {
    return getNumberOfUsers();
  }
  
  return convertedNoOfUsers;
}

function getUserGrade(userId) {
  const input = prompt(`Enter user ${userId} grade`);
  const convertedInput = parseInt(input);

  if (!isValidInput(convertedInput)) {
    return getUserGrade(userId);
  }
  
  return convertedInput;
}

function calculateAverageGrade() {
  const totalNoOfUsers = getNumberOfUsers();
  let sumOfGrades = 0;
  
  for (let currentUser = 1; currentUser <= totalNoOfUsers; currentUser++) {
    const input = getUserGrade(currentUser);
    console.log(`Enter grade ${currentUser}: ${input}`);
    sumOfGrades += input;
  }

  // console.log(sumOfGrades/totalNoOfUsers);
  
  return sumOfGrades/totalNoOfUsers;
}

console.log(`The average score is: ${calculateAverageGrade()}`);
```
