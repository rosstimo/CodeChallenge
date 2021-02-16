# CodeChallenge
## Challenge 1
* Write a generic function to convert a string to a 32-bit integer. 
* The function will take two arguments:
* a string to be converted
* an integer variable that will be updated to the converted value and passed back to the caller
* The function will return a string.
* If the conversion result is:
* success:  Return an empty string
* If the string to be converted is blank: Return "is empty"
* If the conversion fails due to bad data: Return "must contain a number"
* Use the following to create your code: 

```
Private Function ValidateAndConvert(convertThisString, toThisInteger)
        Try
        
        Catch ex As Exception
        
        End Try
        Return message$
End Function
```
