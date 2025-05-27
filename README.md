# Automatic-Code-Correction-via-Agentic-System

1)The implemented agent is designed using LangChain and is capable of automatically detecting and fixing a single-line bug in a given raw Python code. In addition to correcting the bug, the agent also performs validation to ensure the fix is functional. When predefined test cases are not available, the agent intelligently generates and runs a set of assumed test cases using the integrated interpreter tool. This interpreter, combined with the agent’s reasoning capabilities, allows for effective and automated evaluation of the program's correctness.

2)When a Python file from the QuixBugs dataset is provided, the agent performs the following steps:
Reads the buggy program using a Python file reading utility.
Identifies and fixes the single-line bug in the code.
Writes the corrected version to the fixed_programs folder.
Validates the fix by executing the tester.py script on the modified file.

As output, the agent provides:

*The final fixed version of the code.

*The detected bug class (from a set of 14 predefined bug classes).

*The original buggy line and its corrected version.
