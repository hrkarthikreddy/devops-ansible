# Ansible Vault Usage Commands

**NOTE:** Uses community.general.htpasswd (install with ansible-galaxy collection install community.general if needed).

ansible-playbook -i inventory playbook_vault.yml --ask-vault-pass



#### 1. create
**Usage:**
        ansible-vault create <filename>

**Purpose:**
Creates a new file and immediately opens it in your default editor for you to add sensitive content, which will be saved encrypted.

#### 2. edit
**Usage:**
        ansible-vault edit <filename>

**Purpose:**
Opens an existing encrypted file in your editor, allowing you to view and modify its contents securely. The file remains encrypted after saving.

#### 3. view
**Usage:**
        ansible-vault view <filename>

**Purpose:**
Decrypts and displays the contents of an encrypted file in a read-only mode, without editing or decrypting the file on disk.

#### 4. encrypt
**Usage:**
        ansible-vault encrypt <filename>

**Purpose:**
Encrypts an existing plaintext file, replacing it with an encrypted version.

#### 5. decrypt
**Usage:**
        ansible-vault decrypt <filename>

**Purpose:**
Decrypts an encrypted file, returning it to plaintext.

#### 6. rekey
**Usage:**
        ansible-vault rekey <filename>

**Purpose:**
Changes the password used to encrypt an existing vault file, useful for rotating secrets.

#### 7. encrypt_string
**Usage:**
        ansible-vault encrypt_string 'plaintext' --name 'var_name'

**Purpose:**
Encrypts a single string and outputs it as an encrypted variable, which can be pasted directly into playbooks or variable files.

### Common Options for All Commands
        --ask-vault-pass or -J: Prompt for the vault password interactively.

        --vault-password-file <file>: Read the vault password from a file for automation.

        --vault-id <id>: Use multiple vault identities for advanced workflows.

        -v: Increase verbosity for debuggin