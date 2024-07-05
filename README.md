### README.md

# User Management Script

This script automates the creation of users and groups on a Linux system. It reads input from a specified file, creates users, assigns them to groups, generates random passwords, and logs actions. The script ensures secure storage of passwords and maintains logs for audit purposes.

## Features

- Creates users from an input file.
- Assigns users to multiple groups.
- Generates random passwords for users.
- Logs user creation and group assignments.
- Stores passwords securely.
- Checks if users and groups already exist to prevent duplication.

## Requirements

- Linux operating system
- Bash shell
- `openssl` for password generation
- `sudo` privileges

## Usage

1. **Clone the repository**:
    ```sh
    git clone https://github.com/yourusername/user-management-script.git
    cd user-management-script
    ```

2. **Prepare the input file**: 
   The input file should contain usernames and groups in the following format:
    ```
    username1;group1,group2
    username2;group1
    username3;group2,group3
    ```
   Save this file as `input_file.txt`.

3. **Make the script executable**:
    ```sh
    chmod +x user_management.sh
    ```

4. **Run the script**:
    ```sh
    sudo ./user_management.sh input_file.txt
    ```

## Files

- `user_management.sh`: The main script file.
- `input_file.txt`: Example input file (you need to create this with your user data).

## Logging

- Log file: `/var/log/user_management.log`
- Password file: `/var/secure/user_passwords.csv` (permissions are set to `600` for security)

## Example

1. **Sample Input File (`input_file.txt`)**:
    ```
    alice;developers,admins
    bob;developers
    charlie;admins,users
    ```

2. **Run the Script**:
    ```sh
    sudo ./user_management.sh input_file.txt
    ```

3. **Check Log File**:
    ```sh
    cat /var/log/user_management.log
    ```

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

---
