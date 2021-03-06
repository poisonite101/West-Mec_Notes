# Intro to Debugging
* Programing languages have syntax rules
* Logic
     - Order in which various program parts run (execute)
* Bug
    - Any program error
        - Causes program to function incorrectly due to incorrect syntax or flaws in logic

* Debugging
    - Process of tracing and resolving errors in a program

# Understanding syntax errors
* Syntax errors
    - occur:
        - when interperter fails to recognize code
    - causes:
        - incorrect use of JavaScript
        - References to non-existent objects, methods, variables, etc...

* Runtime errors
    - Occur:
        - When interperter encounters a problem while program exdcuting
            - not nessessarly JS language errors
        - When interperter encounters code it cannot execute
        - Run-Time error can be caused by a syntax error
* Logic Errors
    - Flaws in a program's design
        - prevents program from running as anticipated
    - "Logic" reference
        - Excecution of program statements and procedures in the correct order to produce the desired results
    - EX: multiplying instead of dividing:
        + let ratio = 10 * 2; console.log("10 divided by 2 is " + ratio);
    - EX: infinite loop
        + for (var count = 0; count>= 0; count) {console.log("we have liftoff in " + count)};

# Interpreting Error Messages
* First line of defense in location bugs:
    - browser console dispalys
        - line number where error occured
        - error descripton
* Run-time errors
    - Erro messages generated by a web browser
        - can be caused by syntax errors but not by logic errors

* Example:
    + function missingCloseBracket() {
        var message = "this function is missing a closing brace.";
        window. alert(message);

* Error Message
    - Displays error's general location in a program
        - not an exact indicator
* Browsers do not strictly enforce JS syntax
* mitigating bugs in JS programs
     - Always good syntax
     - Throughly test with every browser type/version
        - Test browser if used by more than 1 percent of the market

# Using basic debugging dechniques
* Syntax errors can be difficult to pinpoint
* THere are a few common techniques that are helpful in tracking down bugs

# Tracing erros with the window.alert() method
* Tracing
    - examining statements in an executing program
* Window.alert() method
    - a useful way to trace JS code
    - Place at different points within program
    - used to dispaly variable or array contents or value returned from a function
* use multiple window.alert() methods
    - check values as code executes
* example: function not returning the correct result of 485
    - use the alert to check on the code during different parts of the code
    - the method "pauses' the program untill you dismiss the alert allowing you to check the program at different points
    + Ex:
        + function calculatePay() {
            var payRate = 15; numHours = 40;
            var grossPay = payRate * numHours;
                window.alert(grossPay);
        }
* Drawback
    - must close each box for code to cintinue executing
        - ca be slower than other methods
* use slectively at key points
* place debugging code at different indent level to distungusih from prrogram code


# tracing erros with the console.log() method
* trace a bug by alayzing a list of values
* logging
    - writing values directly to the console using the console.log() method
    - syntax: console.log(value);
    - can log a string literal, var, or combo
* drawbacks
    - can be clunky to retype
    - may help narrow down error but wont tell why it errors
    - cant help in large loops because it happens too often to disseminate (false)
* advantages:
    - can use strings to describe what the value should be or describe what it's ablout
    - can create list of things
    - use it please

# using comments to locate bugs
* Another method to locate bugs is to comment out problematic lines
* this helps isolate statements causing erros
* when erro message first recieved
    - start by commenting out the only statement specified by the line number in the error message
    - continue commenting lines untill error eliminated

* Drawbacks
    - commented code doesnt run so you cnt be sure code is doing what you want it to
* advantages
    - can allow youto test other parts of the code and come back later to fix

# combining debugging techniques
* combine to aid in serarch for errors
*Ex:
    - use comments combined with an elert box or log message to trace erros in the calculate() function

# Dependencies
* replationship in which one statement depends on another statement executing successfully
* Can make debugging more challenging 
* important to retest program after fixing a bug to ensure other parts aren't affected bt change

# Tracing erros with debug tools
* avaible in current versions of all modern browers
* accessible through the same panel that opens when opening the console

* examining code manually
    - usally first step taken with a logic error
    - works fine with smaller programs

* debugging tools
    - help trace each line of code
    - more efficient method of finding and resolving logic errors

# setting breakpoints
* break mode
    - temporally suspension of program execution
    - used to monitor values and trace program execution
* breakpoint
    - statement where execution enters break mode
* when program paused at a breakpoint
    - use debug tools to trace program execution

# Clearing Breakpoints
* To clear a breakpoint
    - Clear the line number again

* To clear ALL breakpoints
    - Right-click any breakpoints
    - Click "Remove all breakpoints" or "Delete all"

# Stepping through your scripts

* Stepping into
    - Executiong an individual line of code
        - pauses until instructed to continue
    - debugger stops at each line within every function
* Stepping over
    - Allows skipping of function calls
    - Program still executes functions stepping over
* Stepping out
    - Executes all remaining code in the current function
    - debugger stops at next statement in the calling function

# Tracing Variables and Expressions
* Variables list
    - Displays all local variables within the currently executing function
    - Shows how different values in the currently executing functuion affects the program execution
* watch list
    - monitors variables and expressions in break mode

# Tracing variables and expressions
* TO add an expression to the watch list
    - locate an instance of the epxression in the program
    - select it and copy it to the clipboard
    - click "click to add"(IE) or "Add watch expression" (Firefox & Chrome)
    - Paste expression from clipboard
    - press enter

# Examining the call stack
* Call stack
    - ordered lists of which procedures (functions, methods, event handlers) have been called but haven't finished executing
* Each time a program calls a procedure it's added to the top of the call stack

# Handling exceptions and errors
* Bulletproofing
    - writing code to anticipate and handle potential problems
    - one technique:
        - validate submitted form data

* Exception handling
    - allows programs to handle errors as they occur in program execution
* exception
    - error occurring in a program

# Throwing Exceptions
* Execute code containing an exception in a try statement
* Throw statement
    - specifies an error message in case an error that occurs within a try block
    + try{
        var lastName = document.getElementById("lName").value;
        if(lastName === ""){
            throw "Please enter your last name.";
        }
    }

# Catching Exceptions
* Use a catch statement
    - handles or "catches" the error
* catch(error){
    statements;
}
+ catch (lNameError) {
    window.alert(lNameError);
    return false;
}

# Executing final exception Handling tasks
* finally statement
    - executes regardless of whether its associated try block throws an exception
    - used to perform some type of cleanup
        - or any necessary tasks after code evaluated with a try statement
    + finally {
        output.innerHTML = "";
    }

# Implementing custom error handling
* Primary purpose
    - prevent users from seeing erros occurring in programs
    - provide graceful way to handle errors
* reason for using exception handling with JS
* programmers may write their own error-handling code
    - can write user-friendly messages
    - provides greater control over any errors

* Writing custom error-handling functions
    - JS interpreter automatically passes three arguments to the custom error handling unction
        - error message, url, line number
    - use these values in custom error handling function
        - add parameters to function definition
    - use parameters in the function
         - show a user the location of any JS errors that may occur

# Additional debugging techniques

* includes
    - checking HTML elements
        - If a bug cannot be located using methods in this chapter
            - perform a line by line analysis of the HTML code
            - ensure all nessessary opening and locating tags included
        - use code editor specialized for web development
            - highlights syntax error as you type
        - use the w3c markup validation service to validate a web page

    - analyzing logic
        - Some JS code erros stem from logic problems
            - can be difficult to spot using tracing techniques
        - analyze each statement on a case-by-case basis

    - testing statements with console command line
        - Console command line
            - testing and executing JS statements
                - without HTML document or JS source file
            - useful if trying to construct the correct syntax for a mathematical expression
        - Enter JS statement at cmd line in web browser console
        - Including multiple statements at the command line
            - separate statements ith the semicolon

    - using the debugger statement
        - When you include the debugger statement in your code
            - web browser stops executing JS code when it reaches the debugger statement statement
            - equivalent of a breakpoint that's part of the JS code

    - executing code in strict mode
        - Removes some features from JS
        - Requires more strict syntax for other features
            - ex: must always use var to declare vars
        - man removed or altered features in strict mode are known to cause hard to find bugs
        - include the statement "use strict:;
        - include at start of script section that requests strict mode for all code in that section
        - including at start of code block in function requests strict mode for that function only

    - linting
        - Running code through a program that flags some common issues tht may affect code quality
        - JSLint is a commonly used linting program
        - similar result to using strict mode
        - this is a great way to check for logical misspellings. it will output a list of variables

    - reloading a web page
        - Usally click the browser reload or refresh button
        - web browser cannot alway completely clear its memory
            - remnants of an old bug may remain
            - force web page reload
                - hold shift key and click the browser's refresh button
        - May need to close browser window completely
        - may need to delete frequently visited web pages