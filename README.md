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
***
## Challenge 2
* Use the test sub to verify your code
* Do Not Modify The Test Code!!
* This code will test your conversion function from Challenge 1
* modify your ValidateAndConvert() function until it passes all tests
```
Private Sub TestValidateAndConvert()
        Dim count As Integer = 0
        Dim result As Integer = 0
        Dim pad As Integer = 15
        Dim report As String = ""
        Dim temp As String = ""
        Dim testData = New String(4, 4) {
            {"5", "2", "17", "8", "42"},
            {"6.7", "3.14", "5.4", "5.5", "0.125"},
            {"-21", "-32.1", "-4", "-4.5", "-4.4"},
            {"", "", "", "", ""},
            {"True", "False", "lOOlO", "9O2lO", "dog"}}
        For row = 0 To 4
            For column = 0 To 4
                result = 0
                temp = ValidateAndConvert(testData(row, column), result)
                report &= ("Trying: " & testData(row, column)).PadRight(pad)
                If row < 3 Then
                    If CStr(CInt(testData(row, column))) <> CStr(result) Or temp <> "" Then
                        report &= " TEST FAIL" & vbNewLine
                        report &= ("Result is: " & CStr(result)).PadRight(pad) & " : " & temp & vbNewLine
                        report &= ("Should be: " & CStr(CInt(testData(row, column)))).PadRight(pad) & " : " _
                        & "<Empty>" & vbNewLine
                    Else
                        report &= " TEST PASS" & vbNewLine
                        count += 1
                    End If
                ElseIf temp <> "is empty" And row = 3 Then
                    report &= " TEST FAIL" & vbNewLine
                    report &= ("Result is: " & CStr(result)).PadRight(pad) & " : " & temp & vbNewLine
                    report &= ("Should be: " & CStr(0)).PadRight(pad) & " : " & "is empty" & vbNewLine
                ElseIf temp <> "Must contain a number" And row > 3 Then
                    report &= " TEST FAIL" & vbNewLine
                    report &= ("Result is: " & CStr(result)).PadRight(pad) & " : " & temp & vbNewLine
                    report &= ("Should be: " & CStr(0)).PadRight(pad) & " : " & "Must contain a number" _
                    & vbNewLine
                Else
                    report &= " TEST PASS" & vbNewLine
                    count += 1
                End If
            Next
        Next
        Console.WriteLine(report & "Passed " & CStr(count) & " of 25 tests. Score: " _
            & CStr((count / 25) * 100) & "%")
        MessageBox.Show("Passed " & CStr(count) & " of 25 tests. Score: " _
            & CStr((count / 25) * 100) & "%")
    End Sub
```
***
