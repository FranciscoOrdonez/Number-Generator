# Number-Generator
A digit only keyboard contains 10 digits from 0 to 9. They all exists within one line. Given a string of 10 digits ilustrating how the keys are positioned. To type a digit your start from index 0 to the index of the target digit. It takes |a - b| milliseconds to move from index a to index b. Write a function to calculate the number of milliseconds needed to type a number with one finger.

Example1: input: digits '0123456789' and num_value = '210'. output: 4

Example2: input: '8459761203' and num_value='5439'. output: 17

Constrains: digits.length = 10, digits contains each digit(0-9) , exactly once in some order, 1 <= num_value <=10**4

APPROACH 1

Get strings 'digit' where keys are positioned, and 'num_value' where the number is located, and pass it to a function

initiate 'sum_values', sum of values as zero, and first value of iteration 'first_value' to zero.

iterate number 'num_value'. If, for example, 'num_value' has three digits, it iterates three times.

get the digit's index value with iteration number. For example, if we are iterating number 5, we look at the index of this number en string 'digit'.

We make a substraction absolute value, between 'first value' minus digit's index value which is the number of milliseconds of the iteration, represented by 'iteration_sum'

Sum total number of millisecond, with 'sum_values' and 'iteration_sum', which is the total number of milliseconds from all digits iterated.

put the digit's index values as 'first_value' and continue iteration.

At the end of iteration, return sum of values "sum_values'.

Reasoning: You can write a function that takes in two parameters, the "digit" string and the "num_value" string. The function should first initialize a variable "sum_values" to zero and "first_value" to zero. Then, it should iterate through each character in the "num_value" string, starting from the first character. For each character, it should find the index of that character in the "digit" string and calculate the difference in index between the current character and the previous character. Then, it should add that difference to the "sum_values" variable. Finally, the function should return the "sum_values" variable as the output.

TEST CASES

Input: digit = '0123456789' and num_value = '210'. Output= 4
Reasoning: We are analyzing the total number of milliseconds to move number '210' with index values on digit '0123456789'. Beginning we put zeros in values of first_value and sum of values, then we get digit '2', go into digit to find index digit, which is two, absolute substract zero minus two which is two, total sum number of milliseconds of iteration which is two, and finally move the digit's index value of 2 to first_value. Then iterate to digit '1'(now we have been iterated '21' out of '210'), and get the index, which is '1' and absolute substract two minus 1 which is one, total sum number of milleseconds of iteration which is two plus one, getting three,move the digit's indedd value of 1 to first value, finally we iterate digit '0' and get the index '0' and absolute substract 1 minus 0 which is 1, and sum total three plus one, finally get total milliseconds of four and return.

Input: digit: '8459761203' and num='5439'. Output: 17
Reasoning: We have to move number '5439' with index '8459761203' and count total of milliseconds. For that, start with digit "5"(1rst. out of 5439'), go to digit index digit[5] which is [845..] in position 2, abs.sub |0-2| total 2,1st v=2, digit "4"(2nd.out of 5439'), go to digit index digit[4] which is [84...] in position 1, abs.sub |2-1|=1 sum 2+1=3,1st v=1 , digit "3"(3rd.out of 5439'), go to digit index digit[3] which is [..203] in position 9,abs.sub |1-9|=8 sum 3+8=11, 1st v=9, digit "9"(4rd.out of 5439'), go to digit index digit[9] which is [..203] in position 3,abs.sub |9-3|=6 sum 11+6=17. Finally return 17 as total milliseconds.

Check the code [here](code)
