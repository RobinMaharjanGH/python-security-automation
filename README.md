# Python Automation: Algorithm for File Updates (Access Control)

## Project Description
In this project, I developed a Python script to automate updates to an access control file (`allow_list.txt`). This automation ensures that restricted servers only accept traffic from authorized, active IP addresses, directly enforcing the **Principle of Least Privilege** and maintaining robust network security boundaries.

## Security Objective
Manual tracking of user access lists introduces human error and security gaps. The goal of this automation is to parse a system's network whitelist, cross-reference it with an external removal list (such as decommissioned assets or terminated employees), and immediately revoke network access.

## Core Cybersecurity Concepts Applied
*   **Identity & Access Management (IAM):** Dynamically adjusting whitelists to restrict unauthorized network access.
*   **Attack Surface Reduction:** Quickly removing stale assets to prevent unauthorized entry.
*   **Secure File Handling:** Implementing safe Python paradigms (`with open`) to ensure file integrity during reads and writes.

## How the Script Functions
1.  **Opening the File:** Uses Python's `with` statement to securely open the `allow_list.txt` target file in read mode.
2.  **String Parsing:** Reads the file contents as a single string and converts it into an iterable Python list using `.split()` to isolate individual IP addresses.
3.  **Iterative Filtering:** Loops through the allowlist and cross-references each address against a `remove_list`. If a match is found, the address is stripped from the list using `.remove()`.
4.  **Rewriting & Enforcing:** Converts the list back into a string using `" ".join()` and overwrites `allow_list.txt` to lock in the new security parameters.
