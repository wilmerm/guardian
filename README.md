# Secure Encryption and Deletion Application

This Python application allows you to securely encrypt files and directories using the **Fernet** library and permanently delete them with the **shred** command. It is useful for protecting sensitive data and ensuring it cannot be recovered.

## **Main Features**

- **Secure Encryption:** Uses the Fernet library to encrypt files and directories with a user-provided key.
- **Permanent Deletion:** Securely removes files and directories using the **shred** command.
- **Recursive Processing:** Supports encrypting and deleting files within directories recursively.
- **User Confirmation Options:** Can be configured to require user confirmation before encrypting or deleting files.

## **Requirements**

- Python 3.x
- Required libraries: `cryptography`, `hashlib`

## **Usage**

### **Using `main.py` and `guardian.sh`**

The `main.py` file is the main entry point for executing the application. It allows you to run encryption, decryption, and secure deletion commands from the command line.

Additionally, the `guardian.sh` Bash script simplifies command execution. You can use it for quick access to application commands.

To execute a command using `guardian.sh`, use the following format:

```sh
./guardian.sh [COMMAND] [OPTION1] [OPTION2]
```

Example: Encrypt a file

```sh
./guardian.sh encrypt /path/to/file secret_key
```

---

### **Encrypting Files and Directories**

You can encrypt files and directories using the `encrypt` command. The function processes the specified path and encrypts all files found. If the path is a directory, it will encrypt all files and subdirectories recursively.

**Example:**

```py
key = 'secret_key'
path = '/path/to/file_or_directory'
encrypt(path, key)
```

---

### **Decrypting Files and Directories**

To decrypt encrypted files, use the `decrypt` function. Like encryption, this function can process directories recursively.

**Example:**

```py
key = 'secret_key'
path = '/path/to/file_or_directory'
decrypt(path, key)
```

---

### **Secure File Deletion**

Files and directories can be securely deleted using the `secure_delete` function. This function relies on the **shred** command and should be run with administrator permissions (`sudo`) to ensure secure deletion. You can configure whether user confirmation is required before deletion.

**Example:**

```py
path = '/path/to/file_or_directory'
secure_delete(path)
```

---

### **Encrypting and Decrypting Text**

You can also encrypt and decrypt text using the `encrypt_text` and `decrypt_text` functions. These functions are useful for protecting messages and sensitive data.

**Example:**

```py
key = 'secret_key'
text = 'This is a confidential message.'
encrypted_text = encrypt_text(text, key)
```

---

## **Setup**

Ensure the required libraries are installed using the following command:

```sh
pip install -r requirements.txt
```

If you plan to use **secure deletion**, make sure you have administrator (`sudo`) privileges.

---

## **Contributing**

If you'd like to contribute to this project or report an issue, feel free to open an issue or submit a pull request on GitHub.

---

## **License**

This application is distributed under the **MIT License**.