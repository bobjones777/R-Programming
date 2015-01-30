## More Tests for Programming Assignment 3 of R Programming

There are 10 tests for Programming Assignment 3 of R Programming. I think more tests are needed to testify that 
your functions satisfy completely the requirements of the assignment. So I modified some data in 
*outcome-of-care-measures.csv* and added two kinds of tests. One is used when there is a tie for the given outcome; 
another is used when all the outcomes in the given state are Not Available. The tests are as below.

**1\.	Tests and Output for best.R**

    > best("AL", "heart attack")
    [1] "ATMORE COMMUNITY HOSPITAL"

    > best("AK", "heart attack")
    [1] NA

**2\.	Tests and Output for rankhospital.R**

    > rankhospital("AK", "heart attack", "worst")
    [1] NA

    > rankhospital("AK", "heart attack", "best")
    [1] NA

    > rankhospital("AL", "heart attack", "best")
    [1] "ATMORE COMMUNITY HOSPITAL"

    > rankhospital("AL", "heart attack", 11)
    [1] "HIGHLANDS MEDICAL CENTER"

**3\.	Tests and Output for rankall.R**

    > head(rankall("heart attack", "best"), 2)  
                       hospital state  
    1                      <NA>    AK  
    2 ATMORE COMMUNITY HOSPITAL    AL

    > head(rankall("heart attack", "worst"), 2)
                            hospital state
    1                           <NA>    AK
    2 HELEN KELLER MEMORIAL HOSPITAL    AL
    
    > head(rankall("heart attack", 11), 2)
                      hospital state
    1                     <NA>    AK
    2 HIGHLANDS MEDICAL CENTER    AL
