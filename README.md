# UserInputProgram_Cpp

1.) Program: 
Create a C++ program that will obtain input from a user and store it into the provided CSC450_CT5_mod5.txtDownload CSC450_CT5_mod5.txt file. 

2.) Download File:
Download CSC450_CT5_mod5.txtDownload CSC450_CT5_mod5.txt file. 
Your program should append it to the provided text file, without deleting the existing data: 
  --> Store the provided data in the CSC450_CT5_mod5.txt file.
  --> Create a reversal method that will reverse all of the characters in the CSC450_CT5_mod5.txt file and store the result in a CSC450-mod5-reverse.txt file.


  Pseudocode:

  BEGIN PROGRAM
  
>> Step 1: Create mutex for file protection
  Create Global mutex called fileMutex

>> Step 2: Prompt user for input
  Display:
    "Enter text to append to file:"

  Read entire line from user

  Store Input in variable
    userInput

>> Step 3: Append input into original file
  Acquire mutex using lock_guard

  Open file:
    CSC450_CT5_mod5.txt
    
  Open in APPEND mode

  IF file opens successfully THEN
  
    Write userInput
    
    Write newline
    
    Close file
    
  ELSE
  
    Display error message
    
    Exit program

  ENDIF
  
  lock_guard automatically releases mutex

>> Step 4: Read Entire contents of file
  Acquire mutex using lock_guard

  Open file: 
    CSC450_CT5_mod5.txt

  Open for reading

  IF file opens successfully THEN

    Create string:
      OriginalText
      
    Read entire file contents

    Store contents into OriginalText

    Close file
    
  ELSE

    Display error message

    Exit program

  ENDIF

  lock_guard automatically releases mutex

>> Step 5: Reverse file contents
  Call reverseText() method

    Pass originalText to method

    Method creates string:
    reversedText

    Method reverses every character in originalText

    Method returns reversedText

>> Step 6: Write reversed content to a new file
  Acquire mutex using lock_guard

    Open file:
      CSC450-mod5-reverse.txt

    Open for writing

    IF file opens successfully THEN

      Write reversedText

      Close file
      
    ELSE

      Display error message

      Exit program

    ENDIF

    lock_guard automatically releases mutex

>> Step 7: Display success message
  Display:
    "Data successfully appended.

  Display: 
    "Reversed file successfully created."

  END PROGRAM


    
