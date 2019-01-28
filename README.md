# quiz-6-corrections
Q1: Consider the following code segment.

int index = 7;
values[index] = values[currentSize - 1];
values[currentSize - 1] = null;
currentSize--;
Which of the following most accurately describes the code segment above and the array it modifies?

My Answer: The seventh primitive value in an array is overwritten (i.e., removed) by the last primitive value in an array. The last primitive value in the array is set to the default value of 0.

Correct Answer: The eighth object in an array is overwritten (i.e., removed) by the last object in an array. The last object in the array is set to the default value of null.

Why It's Correct: Since it is at index 7 the string must have a length of 8. We then know that a value is being removed so it is being overwritten. Which would cause it to be set to null.


Q4: Consider the following method, which is designed to return the maximum value in an array.

/**
 * Returns the maximum value in the array.
 * Precondition: values != null && values.length > 0
 */

public int findMaximum(int[] values) {
    int max = 0;

    for (int i = 0; i < values.length; i++) {
        if (values[i] > max) {
            max = values[i];
        }
    }

    return max;
}
Which of the following calls to findMaximum demonstrates that it does not work as expected?

My Answer: findMaximum(new int[] { -5, 1, -4, 2, -3 })

Correct Answer: findMaximum(new int[] { -5, -1, -4, -2, -3 })

Why It's Correct: It is correct because the option includes all negatives. Negatives in java for this problem would cause this to not work as expected. This is due to the fact that negatives work diffrently in the loop.



Q8: I need to write a method designed to compute and return a student's average based on a list of grades. Which of the following methods will accomplish this task for all possible inputs (including null or empty arrays)? Select all that apply.

My Answer: public double getAverage(double[] grades) {
    double sum = 0;

    for (int i = 0; i < grades.length; i++) {
        sum = sum + grades[i];
    }

    return sum / grades.length;
}

Correct Answer: public double getAverage(double[] grades) {
    double sum = 0;

    if (grades != null) {
        for (int i = 0; i < grades.length; i++) {
            sum = sum + grades[i];
        }

        if (grades.length > 0) {
            return sum / grades.length;
        }
    }

    return -1;
}
  
public double getAverage(double[] grades) {
    double sum = 0;

    if (grades != null) {
        for (double grade : grades) {
            sum = sum + grade;
        }

        if (grades.length > 0) {
            return sum / grades.length;
        }
    }

    return -1;
}

Why It's Correct: Both are ways that return student averages based on grades. They have the sum as the current grade plus the previous grade. Then it divides it by the length of the array and then divides it by the sum. 

Q12: Consider the following code segment.

int[] numbers = new int[25];
System.out.println(numbers[10]);
What is printed to the console as a result of executing this code?

My Answer: Nothing, because a compilation error occurs. 

Correct Answer: 0

Why It's Correct: This is correct because the defeault null value for an int is zero. It would not be an error because the array has a given length. We have to assume there is nothing at that index so the value would be zero.


Q14: I need to populate an array of integers that will represent each of the perfect squares between 1 and 10. Which of the following code segments below accomplishes that task? Select all that apply.

My Answer: int[] perfectSquares = new int[10];

for (int i : perfectSquares) {
    perfectSquares[i] = i * i;
}

Correct ANswer: int[] perfectSquares = new int[10];

for (int i = 1; i <= 10; i++) {
    perfectSquares[i - 1] = i * i;
}

  
int[] perfectSquares = new int[10];

for (int i = 0; i <= 10; i++) {
    perfectSquares[i] = (i + 1) * (i + 1);
}

  
int[] perfectSquares = new int[10];

int i = 1;
while (i <= 10) {
    perfectSquares[i - 1] = i * i;
}


Why It's Correct: It is correct because it populates values from 1 to 10. They each use a method that takess values from 1 to 10. While the inccorect choice includes 0 in its repsonse.
