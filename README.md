# Biased-Random-Number-Generator-master
Random No. Generator (73 % Biased)
# Random Number Generation (73% Biased)
Write a custom random number generation algo which should be 73% biased to the higher number. Like if I want a random number between 1 to 10 100times then it should give number more than 5 73times and less than 5 27times.

Algorithm:

Step 1 : User inputting the values:                                     
        	a => lower bound                      
        	b => upper bound
       
Step 2 : Calculating mid value for biased probability                                      
       		mid_value := (a+b)/2

Step 3 : Calculating the range of biased number using mid_value (excluding mid_value) eg. 73% above 5 and 27% below5                                 
        	minimum_list := minimum_list will contain value from range 'a' to mid_value-1                                                  
        	maximum_list := maximum_list will contain value from range mid_value+1 to b+1

Step 4 : Calculate random number using Linear congruential generator(False-Random No. Generation Algorithm)  

		      while(length of maximum_list =! 73)	
			     number = (current_time +increment_value * multiplier) % mod
			     value = number/mod
			     value_in_range = (mid_value+1) + value * ((b+1)-(mid_value+1))
			     add value_in_range to maximum_list

		      while(length of minimum_list =! 27)	
		       number = (current_time +increment_value * multiplier) % mod
			     value = number/mod
			     value_in_range = a + value * ((mid_value-1)-a)
			     add value_in_range to min_list

Step 5 : Show minimum_list , maximum_list and final_list (where final_list is the concatenation of the minimum_list and maximum_list)

Explanation:
1. Initially, take the input from user i.e., lower bound and upper bound. These bounds will decide the range of the no. of values. 
2. Calculate the mid_value from upper and lower bound, to separate the range in two parts i.e., upper range and lower range.
3. Then Create two list, named minimum_list and maximum_list. Minimum_list will contain values from lower bound to mid value(excluded : say mid_value-1). Maximum_list will contain values from mid_value (excluded : say mid_value+1) to the upper bound.
4. Start a while loop1 until and unless the length of maximum_list becomes 73.
     In this loop, we will create a random no. using the Linear Congruential Generator (LCG) method in which  an equation is used :
      number = (increment + current time * multiplier) % mod 
and then random no. generated from this value is put into equation:
    value =  number/mod
which will give the output to the vakue between 0 and 1 to calculate the no. in given range.
then add final value to the maximum_list.
5. Start the second loop i.e., loop2 until and unless the length of minimum list becomes 27.
    Perform the same procedure as loop1.
    then add the final value to minimum_list.
5. Print Both the lists i.e., minimum_list and maximum_list.
6. Then print final_list which is the concatenated list of maximum_list and minimum_list.

