// Log the input till the count reaches at 5

// Need loop

// With while

while(condition) {
  // Statements
}

let i = 1;

while(i <= 5) {
  console.log(i);

  i++;
}

// Next statement


// Keep retrying the API call till you get the updated record (Pool the data)

let recordExists = false;
let retryCount = 0;

while(recordExists === false) {
  if (retryCount === 10) {
    break;
  }
  console.log('Count', retryCount);
  retryCount++;
}


// For loop
for (initialization; condition; update) {
  // code to be executed repeatedly
}

for (let i = 1; i <= 5; i++) {
  console.log(i, j);
}

let i;
for (i = 1; i <= 5; i++) {
  console.log(i, j);
}


// Skip the lunch for Monday, Wednesday, Friday
let day = 'Saturday';

switch(day) {
  case 'Monday':
  case 'Wednesday':
  case 'Friday':
    console.log('Skip the lunch today!');
    break;
  default:
    console.log('Congratulations you can have your lunch today!');
}
