# Lab Report 5
## Finding the different results 
To find the difference in test results, I used the `diff` command, more specifically, I ran:

`diff markdown-parse/results.txt markdown-parse-their/results.txt`

## Test 1 (File 201)

### Output from other implementation: 

    test-files/201.md [baz]

### Output from my implementation:

    test-files/201.md []

### Expected output
    [foo]: (baz)

    [foo]

As seen above, the output from the other implementation for this test file was `[baz]`, while the output from my implementation returns an empty list `[]`.

My output returns an empty list because the link in the file is invalid and not formatted properly. 

The other implementation can be fixed by accounting for the space between the closing bracket and the opening parenthesis. Thus, a check to search for `](` can be implemented to account for the bug. 

## Test 2 (File 510)

### Output from other implementation: 

    test-files/510.md [/uri]

### Output from my implementation:

    test-files/510.md [/uri]

### Expected output; 
    []

As seen above, both the output from the other implementation and my implementation for this test file was `[/uri]`, which is wrong. The expected output is an empty list `[]`.

The bug exists in my implementation because there isn't a check for the slash. The lack of this check before the string is added to the return array makes it so all links are added, and what is inside the actual link is not considered. Hence, to fix my implementation, a check for the slash before the link is added to the array can be added to get rid of the bug. 

