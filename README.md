# Automatic-Code-Correction-via-Agentic-System

1)The implemented solution is a Multi-Agentic System built using LangChain, enhanced with Google's Gemini API, and supported by custom tools. It is capable of automatically detecting, correcting, validating, and classifying single-line bugs in raw Python code.

Unlike traditional single-agent models, this system leverages a division of responsibility through three specialized agents, resulting in modular, accurate, and explainable debugging.


When a Python file from the QuixBugs dataset is provided, the multi-agent system performs the following steps:

1. Bug Fixing Agent

Reads the buggy program using the custom read_python_file tool.
Analyzes and detects a single-line bug using the Gemini API.
Fixes the bug and writes the corrected version to the fixed_programs/ folder via the write_python_file tool.

2. Validation Agent

Checks for available test cases (tester.py).
If found, executes tester.py <program> to validate the fix.
If not found, intelligently generates and runs assumed test cases using the built-in Riza_code_interpreter for logical verification.

3. Bug Classification Agent

Compares the buggy and corrected lines.
Classifies the fix into one of 14 predefined bug categories (e.g., Off-by-One, Incorrect Operator).
Output
As output, the system provides:

The final fixed version of the code.
The classified bug type from the predefined taxonomy.
The original buggy line and the corrected line for traceability.
Test result summary confirming the functional validity of the fix.
