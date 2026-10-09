# Setting Up Debugging in VS Code

## Task 1 Create a debug configuration

1. Open the 'Run and Debug' view (left sidebar) → 'create a launch.json file' → choose 'Python Debugger (Suggested)' → choose 'Python File' → choose 'Python: Current File'.
2. VS Code creates `.vscode/launch.json`:

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        
        {
            "name": "Python Debugger: Current File",
            "type": "debugpy",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal"
        }
    ]
}
```

This configuration allows you to run and debug the currently active Python file repeatedly.