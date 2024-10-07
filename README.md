# Run-as-Admin

# Batch Script for Requesting Administrative Privileges
This batch script is designed to elevate permissions and request administrative rights (UAC) for running commands that require elevated privileges on a Windows machine. If the script is not executed with administrative rights, it will prompt the user to run it as an administrator. Once administrative privileges are granted, it can execute additional commands or scripts.

# How It Works
Permission Check: The script first checks if it has administrative rights by attempting to access a system folder (%SYSTEMROOT%\system32\config\system).

Prompt for Admin Privileges: If the script doesn't have the necessary privileges, it uses a temporary VBScript (getadmin.vbs) to invoke a User Account Control (UAC) prompt, asking for administrative access.

Re-execution with Admin Rights: If the user approves the prompt, the script re-executes itself with administrative rights.

Clean-Up: After successfully obtaining admin rights, the temporary VBScript is deleted, and the script continues execution.

# Key Parts of the Script
Checking for Admin Rights: The script checks the permissions using the cacls.exe command.

UAC Prompt: If admin rights are not available, the script dynamically creates a VBScript to request elevated privileges using the ShellExecute method.

Temporary VBScript Clean-Up: The temporary VBScript (getadmin.vbs) is deleted after execution to keep the system clean.

Execution of Additional Commands: After gaining admin privileges, additional commands can be added at the bottom of the script, or the script can call other programs.

# Usage
Clone or download the repository.
Open the batch script in a text editor to modify it if needed (for adding additional commands).
Run the batch script by double-clicking it or executing it in the Command Prompt.
If the script needs administrative rights, a UAC prompt will appear. After granting the necessary permissions, the script will continue execution.
Example Use Case
This script can be useful for tasks such as:

Modifying system files.
Installing software.
Running system diagnostics or configurations that require elevated privileges.
# Notes
Ensure that you trust the script before running it with elevated privileges, as it could modify critical system files or settings.
This script will only work on Windows systems that support UAC.
# License
This project is licensed under the MIT License - see the LICENSE file for details.
# Disclaimer
This is for educational purposes only
