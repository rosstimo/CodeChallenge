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
## Challenge 3

```
    'In as few lines as possible produce the same results as the function IsWayTooLong()
    'Hint use a loop and a List or Array
    'Also only have one return statement at the end
    Private Function ShortAndSweet(ByVal numberFromZeroToFifteen As Integer) As String
        'Your code here
    End Function

    Private Function IsWayTooLong(ByVal numberFromZeroToFifteen As Integer) As String
        If numberFromZeroToFifteen = 0 Then
            Return "Your number is: Zero"
        End If
        If numberFromZeroToFifteen = 1 Then
            Return "Your number is: One"
        End If
        If numberFromZeroToFifteen = 2 Then
            Return "Your number is: Two"
        End If
        If numberFromZeroToFifteen = 3 Then
            Return "Your number is: Three"
        End If
        If numberFromZeroToFifteen = 4 Then
            Return "Your number is: Four"
        End If
        If numberFromZeroToFifteen = 5 Then
            Return "Your number is: Five"
        End If
        If numberFromZeroToFifteen = 6 Then
            Return "Your number is: Six"
        End If
        If numberFromZeroToFifteen = 7 Then
            Return "Your number is: Seven"
        End If
        If numberFromZeroToFifteen = 8 Then
            Return "Your number is: Eight"
        End If
        If numberFromZeroToFifteen = 9 Then
            Return "Your number is: Nine"
        End If
        If numberFromZeroToFifteen = 10 Then
            Return "Your number is: Ten"
        End If
        If numberFromZeroToFifteen = 11 Then
            Return "Your number is: Eleven"
        End If
        If numberFromZeroToFifteen = 12 Then
            Return "Your number is: Twelve"
        End If
        If numberFromZeroToFifteen = 13 Then
            Return "Your number is: Thirteen"
        End If
        If numberFromZeroToFifteen = 14 Then
            Return "Your number is: Fourteen"
        End If
        If numberFromZeroToFifteen = 15 Then
            Return "Your number is: Fifteen"
        End If
        If numberFromZeroToFifteen < 0 Then
            Return "Your number is: Too Low"
        End If
        If numberFromZeroToFifteen > 15 Then
            Return "Your number is: Too High"
        End If
    End Function

    'Do Not change this code other that comment/uncomment the lines indicated
    Private Sub GetUserInput()
        Dim tempNum As Integer = 0
        Dim userMessage As String = "Please Enter A Number Between 0 and 15" _
            & vbNewLine & "Type Q to Quit"
        Do
            userMessage = InputBox(userMessage, "Hello", "")
            If userMessage <> "Q" And userMessage <> "" Then
                userMessage = ValidateAndConvert(userMessage, tempNum)
                If userMessage = "" Then userMessage = IsWayTooLong(tempNum)        'Replace this Line
                'If userMessage = "" Then userMessage = ShortAndSweet(tempNum)      'With this one
            End If
        Loop Until userMessage = "Q" Or userMessage = ""
    End Sub

'Use the working code from Challenge 1 and 2
Private Function ValidateAndConvert(convertThisString, toThisInteger)
'your working code
End Function

```
