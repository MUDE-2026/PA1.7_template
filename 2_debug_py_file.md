# Debugging a py file

## Task 1 Set breakpoints and start debugging

1. Open `debug_example.py` and click left of a line number to add a red breakpoint (e.g., on `total = 0`).
2. Start debugging: press F5 or click the green 'Run and Debug' button while `debug_example.py` is active.
3. When execution pauses:
   - Inspect variables in the 'Variables' view.
   - Use the 'Debug Console' to evaluate expressions (e.g., `v`).
   - Use the 'Call Stack' to see how you got here.

## Task 2 Step through code

1. Click 'Step Over' (F10) multiple times: This runs the current line; if it calls a function, executes it without entering and stops at the next line in the same function. Observe how `v` changes and where the exception occurs.
2. Test the other stepping commands:
  - 'Continue' (F5), runs until the next breakpoint, exception or program end.
  - 'Step Into' (F11): Enters the called function and pauses at its first line so you can debug inside it.
  - 'Step Out' (Shift+F11)

## Task 3 Break on exceptions and conditional breakpoints

1. In the 'Breakpoints' view on the bottom left corner, enable breaking on exceptions ('Raised Exceptions' / 'Uncaught Exceptions').
2. Right-click the breakpoint (in the gutter or in the Breakpoints view) → 'Add conditional breakpoint' and enter a condition to check the division by zero:
    - If the breakpoint is inside `compute_ratio()`, use `b == 0` (local parameter in that function).
    - If you prefer to stop at the call site, place a breakpoint on `total += compute_ratio(10, v)` and set condition `v == 0`, then use F11 (Step Into).
  Note: If there is already a breakpoint, right-click and use 'Edit Breakpoint...'.
3. Press F5. Execution pauses when `b` is 0. With exception breakpoints enabled, it also pauses on `ZeroDivisionError` even without a conditional.

## Task 4 Adapt

1. Adapt the code to handle division by zero gracefully, e.g., return 0 instead of raising an exception. While debugging, you can inspect the Variables, which allows you to confirm confirm `a == 10`, `b == 0` at some point. In the Debug Console (in the bottom toolbar) you can debug expressions safely: try `a / (b or 1)` to probe safely.
2. Whenever you're happy with the code, stop debugging (Shift+F5), implement your changes and run the script normally (F5 or Run → Run Without Debugging) to see the output.