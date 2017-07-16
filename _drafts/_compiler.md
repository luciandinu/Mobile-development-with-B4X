
## Compiler

Compiler Warnings

Clicking on the warning will take you to the relevant code.

Ignoring warnings

You, as the developer, can choose to ignore any warning. Adding an "ignore" comment will remove all the warnings for that specific line:

```xojo
Sub UnusedSub(a As Int) 'ignore
```

You can also disable warning from a specific type in the module by adding the #IgnoreWarning attribute.
For example to disable warnings #10 and #12:
Code:

```
#IgnoreWarnings: 10, 12
```

Runtime warnings

Some of the warnings are only checked at runtime. These warnings will appear in the regular logs.
Runtime warnings are only checked in Debug mode.

List of warnings

```
1: Unreachable code detected.
2: Not all code paths return a value.
3: Return type (in Sub signature) should be set explicitly.
4: Return value is missing. Default value will be used instead.
5: Variable declaration type is missing. String type will be used.
6: The following value misses screen units ('dip' or %x / %y): {1}.
7: Object converted to String. This is probably a programming mistake.
8: Undeclared variable '{1}'.
9: Unused variable '{1}'.
10: Variable '{1}' is never assigned any value.
11: Variable '{1}' was not initialized.
12: Sub '{1}' is not used.
13: Variable '{1}' should be declared in Sub Process_Globals.
14: File '{1}' in Files folder was not added to the Files tab.\nYou should either delete it or add it to the project.\nYou can choose Tools - Clean unused files.
15: File '{1}' is not used.
16: Layout file '{1}' is not used. Are you missing a call to Activity.LoadLayout?
17: File '{1}' is missing from the Files tab.
18: TextSize value should not be scaled as it is scaled internally.
19: Empty Catch block. You should at least add Log(LastException.Message).
20: View '{1}' was added with the designer. You should not initialize it.
21: Cannot access view's dimension before it is added to its parent.
22: Types do not match.
23: Modal dialogs are not allowed in Sub Activity_Pause. It will be ignored.
24: Accessing fields from other modules in Sub Process_Globals can be dangerous as the initialization order is not deterministic.
25: Sub '{1}' not found.

'Runtime warnings
1001: Panel.LoadLayout should only be called after the panel was added to its parent.
1002: The same object was added to the list. You should call Dim again to create a new object.
1003: Object was already initialized.
1004: FullScreen or IncludeTitle properties in layout file do not match the activity attributes settings.
```