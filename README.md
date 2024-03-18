  # Regex-AWK Lab

  ## Introduction
  In this lab, You will gain practical knowledge in working with Regular Expressions and some command-based data processing tools like AWK. You will work on the given simple text file (data.txt) and use linux to process the file to answer some required queries.

  ## Lab requirements:
  * You must have linux or WSL to run the commands on the terminal
  * Learn regular expression (Regex) and finish this tutorial <a href="https://regexone.com/">here</a>
  * Gain lots of skills working with AWK from this article (until lession number 13 at least) <a href="https://linuxhandbook.com/awk-command-tutorial/">here</a>
  * Try to work with AWK on this interactive tutorial <a href="https://n8ta.com/projects/awk.html">here</a>

  # Steps to start:
  1- Go to your working directory:
  
  ```bash
  cd <your working dirctory Ex. 'cd C:\docker'>
  ```
  2- create a text file (data.txt for example) and insert the data we will work on:
  
  ```bash
  nano data.txt
  ```
  Then paste the data instide this file and press "ctrl+o" then "enter" then "ctrl+x" to exit
  
  3- To view the data:
  
  ```bash
  cat data.txt
  ```
  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/44eef754-a86f-4c12-94b1-af4774e872e2)

  Now you are ready to work on the quests ⚡✅

  ## Quests:
  a-	Print only the first and last names of all the clients (there must be a space between first and last names):
  
  It can be done in two ways: 

  ```bash
  awk '{print $1, $2}' data.txt
  ```
  ```bash
  awk '{print $1 " " $2}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/28e29847-1cd4-408c-a946-d3e578147e37)


  b-	Same as above but print the names are in reverse order (last name, first name) and make sure there is a comma between last name and first name:

  It can be done like this:

  ```bash
  awk '{print $2 "," $1}' data.txt
  ```
  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/ffda920e-77b0-4c48-b52a-0c6a00ee24b9)

  c-	Print only first name and last name (without header that has the names of the columns: first name, last name, etc):

  It can be done like this:

  ```bash
  awk 'NR>1 {print $1, $2}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/5836abbe-4cbf-40fb-a64f-fa82ed3c84c0)

  d-	Same as above but with numbers indicating the client's order:

  It can be done like this:

  ```bash
  awk 'NR>1 {print NR-1, $1, $2}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/2abeba73-5526-4d35-9fae-9a09b046a14d)

  e-	Print first and last names of customers who are more than 50 years old:

  It can be done like this:

  ```bash
  awk 'NR>1 && $4 > 50 {print $1, $2}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/49d14327-e29f-4ce6-b3af-63e7353741a1)

  f-	Print the first and last names of customers who own more than 10000$:

  It can be done like this:

  ```bash
  awk 'NR>1 && $5 > 10000 {print $1, $2}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/cc04217a-4cc3-4101-992c-d6bee15ae0f8)

  g-	Print the total sum of all money in all the accounts:

  It can be done like this:

  ```bash
  awk '{sum += $5} END {print sum}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/4b4077f5-e035-4bf3-b03c-37ffd6bdf528)

  h-	Print all the information of all accounts whose owner's first name is Chad. (hint. use REGEX):

  It can be done like this:

  ```bash
  awk '$1 ~ /^Chad$/ {print}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/3e4c04c3-760f-4800-9996-d194f0665f78)

  i-	Print all the information of all accounts whose owner's last name ends with the letter r (hint: REGEX):

  It can be done like this:

  ```bash
  awk 'NR>3 && $2 ~ /r$/ {print}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/560b88d1-5a18-45a9-930a-3b75aabf9398)

  j-	Print all the information of all accounts whose owner age has the number for the first and 2nd digits:

  It can be done like this:

  ```bash
  awk '$4 >= 10 && int($4/10) == $4 % 10 {print}' data.txt
  ```

  ![image](https://github.com/BaraSedih11/Regex-AWK/assets/98843912/52307add-42ee-4996-9f1e-a5f4f10b77e4)

  ## Congratulations 🥳💥
  You've completed this lab, I hope you find it helpful, follow me on my github profile to learn more exciting things ⚡💻










  

  


