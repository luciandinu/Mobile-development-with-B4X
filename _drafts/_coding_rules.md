# B4A Documentation

This document describes a series of things related to B4A (B4X) development software with  some basic coding rules and priciples. These rules just tryies to set a common "language" used on all projects developed.  

------
[TOC]
------

## Introduction

## Access modifiers in B4A (B4X)
Comparing to other programming languages like C# or Java, B4A has only 2 access modifiers
Basic4android v2.00 adds two new access modifiers: **Public** and **Private**. This will cover the rules which determine when a variable or a sub can be accessed from outside.

Note that the default accessibility is Public. 

**Variables**
- Activities, services and code modules: process global variables are public by default.
- Activity global variables are always private.

You can hide process global variables by using the Private modifier:
```xojo
Sub Process_Globals
 Dim ThisIsAPublicVariable As String 'public
 Public ThisIsAPublicVariableToo As String 'exactly the same as Dim.
 Private ThisIsAPrivateVariable As String 'private
End Sub
```

- Classes: sames as above for variables declared in Class_Globals.

**Subs**
- Subs declared in Activity and Service modules are private.
- Subs declared in Code modules and Class modules are public by default.
- 
You can hide such subs with the Private modifier:

```xojo
Private Sub ThisIsAPrivateSub(x As Int)

End Sub
```

The Public modifier can also be used (though it doesn't have any effect):
```xojo
'Public subs
Sub S1

End Sub

Public Sub S2
 
End Sub
```

CallSub and CallSubDelayed can be used to call subs in other services, activities and classes. These methods can be used to access both private and public subs.



### General notations

