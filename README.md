<?php

// Problem 1: String Manipulation
function manipulateString($input) {
    // Check if the string contains the word "PHP"
    if (strpos($input, 'PHP') !== false) {
        echo "The input string contains the word 'PHP'.\n";
    } else {
        echo "The input string does not contain the word 'PHP'.\n";
    }

    // Replace all spaces with underscores
    $input = str_replace(' ', '_', $input);

    // Convert the string to uppercase
    $input = strtoupper($input);

    return $input;
}



    
    
  
    
// Problem 2: Form Validation
function validateForm($name, $email, $age = null) {
    $errors = [];

    // Validate name
    if (empty($name) || strlen($name) < 3) {
        $errors[] = "Name is required and must be at least 3 characters long.";
    }

    // Validate email
    if (empty($email) || !filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = "A valid email is required.";
    }

    // Validate age
    if (!empty($age) && !is_numeric($age)) {
        $errors[] = "Age must be a number if provided.";
    }

    return $errors;
}




// Problem 3: Increment/Decrement Operations
function incrementDecrementDemo() {
    $value = 10;
    echo "Initial value: $value\n";

    $value++;
    echo "After increment: $value\n";

    $value--;
    echo "After decrement: $value\n";
}




// Problem 4: Switch Case for Days of the Week
function getDayOfWeek($number) {
    switch ($number) {
        case 1:
            return "Monday";
        case 2:
            return "Tuesday";
        case 3:
            return "Wednesday";
        case 4:
            return "Thursday";
        case 5:
            return "Friday";
        case 6:
            return "Saturday";
        case 7:
            return "Sunday";
        default:
            return "Invalid input. Please enter a number between 1 and 7.";
    }
}



// Problem 5: Pricing System
function calculateTicketPrice($age, $isStudent) {
    $basePrice = 10;
    $discount = 0;

    if ($age < 12) {
        $discount = 0.5;
    } elseif ($age >= 60) {
        $discount = 0.3;
    } elseif ($isStudent) {
        $discount = 0.2;
    }

    $finalPrice = $basePrice * (1 - $discount);
    return $finalPrice;
}



// Problem 6: Pass by Value vs. Pass by Reference
function doubleValue($num) {
    return $num * 2;
}

function doubleReference(&$num) {
    $num *= 2;
}



// Problem 7: Loop with Conditions
function fizzBuzz() {
    for ($i = 1; $i <= 20; $i++) {
        if ($i % 3 == 0 && $i % 5 == 0) {
            echo "FizzBuzz\n";
        } elseif ($i % 3 == 0) {
            echo "Fizz\n";
        } elseif ($i % 5 == 0) {
            echo "Buzz\n";
        } else {
            echo "$i\n";
        }
    }
}



// Problem 8: Returning Values from Functions
function calculateArea($length, $width) {
    return $length * $width;
}

function calculatePerimeter($length, $width) {
    return 2 * ($length + $width);
}




// Problem 9: Bill Splitter
function splitBill($totalBill, $numPeople, $tipPercentage = 10) {
    $totalBillWithTip = $totalBill + ($totalBill * $tipPercentage / 100);
    $amountPerPerson = $totalBillWithTip / $numPeople;
    return $amountPerPerson;
}

// Example usage for each problem:

// Problem 1
$inputString = "Hello PHP World";
echo "Problem 1:\n";
echo "Manipulated string: " . manipulateString($inputString) . "\n\n";

// Problem 2
$name = "John";
$email = "john.doe@example.com";
$age = 25;
echo "Problem 2:\n";
$errors = validateForm($name, $email, $age);
if (empty($errors)) {
    echo "Form is valid.\n";
} else {
    foreach ($errors as $error) {
        echo "$error\n";
    }
}
echo "\n";


// Problem 3
echo "Problem 3:\n";
incrementDecrementDemo();
echo "\n";

// Problem 4
$dayNumber = 3;
echo "Problem 4:\n";
echo "Day of the week: " . getDayOfWeek($dayNumber) . "\n\n";

// Problem 5
$age = 65;
$isStudent = false;
echo "Problem 5:\n";
echo "Ticket Price: $" . calculateTicketPrice($age, $isStudent) . "\n\n";

// Problem 6
$num = 5;
echo "Problem 6:\n";
echo "Double Value: " . doubleValue($num) . "\n";
doubleReference($num);
echo "Double Reference: $num\n\n";

// Problem 7
echo "Problem 7:\n";
fizzBuzz();
echo "\n";

// Problem 8
$length = 5;
$width = 10;
echo "Problem 8:\n";
echo "Area: " . calculateArea($length, $width) . "\n";
echo "Perimeter: " . calculatePerimeter($length, $width) . "\n\n";

// Problem 9
$totalBill = 120;
$numPeople = 4;
$tipPercentage = 15;
echo "Problem 9:\n";
echo "Each person pays: $" . splitBill($totalBill, $numPeople, $tipPercentage) . "\n";
jasssi

?>


