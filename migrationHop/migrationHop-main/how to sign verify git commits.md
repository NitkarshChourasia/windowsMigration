To create signed commits on GitHub using Windows 10 and PyCharm Professional, you need to follow these steps:

1. Install Git and set it up:
   - Download Git for Windows from the official website: https://git-scm.com/download/win
   - Run the installer and follow the instructions to complete the installation.
   - Open a terminal or Git Bash to verify that Git is properly installed by running the command: `git --version`
   - Configure Git with your username and email using the following commands:
     ```
     git config --global user.name "Your Name"
     git config --global user.email "your-email@example.com"
     ```

2. Generate a GPG key:
   - Open a terminal or Git Bash and run the command: `gpg --gen-key`
   - Follow the prompts to generate a new GPG key. Make sure to provide a secure passphrase when prompted.
   - Once the key is generated, run the command: `gpg --list-secret-keys --keyid-format LONG` to list your GPG keys.
   - Look for the key ID (e.g., `sec   rsa4096/XXXXXXXXXXXXXXXX`), and note down the key ID (XXXXXXXXXXXXXXXX in this example).






I apologize for the confusion. Let me provide more detailed steps on how to find the key ID (key fingerprint) for your GPG key:

1. Open a terminal or Git Bash.
2. Run the command: `gpg --list-secret-keys --keyid-format LONG`
3. Look for the line starting with "sec" followed by the key type and key ID.
   - It will look something like: `sec   rsa4096/XXXXXXXXXXXXXXXX`.
   - The key ID is the value after the slash (/), in this example, `XXXXXXXXXXXXXXXX`.
4. Note down the key ID (XXXXXXXXXXXXXXXX in the example) for further configuration.

If you have multiple keys listed, make sure to identify the correct key associated with your GPG keypair. The key ID is unique to each keypair and is used to identify and reference the specific key.






3. Add the GPG key to your GitHub account:
   - Go to your GitHub account settings.
   - Navigate to "SSH and GPG keys" section.
   - Click on "New GPG key" or "Add GPG key".
   - Paste your GPG key into the designated area and save it.

4. Configure Git to use the GPG key:
   - In the terminal or Git Bash, run the command: `git config --global user.signingkey XXXXXXXXXXXXXXXX` (replace XXXXXXXXXXXXXXXX with your GPG key ID).

5. Configure PyCharm to use Git:
   - Open PyCharm Professional and navigate to "Settings" or "Preferences".
   - Go to "Version Control" and select "Git".
   - In the "Path to Git executable" field, provide the path to the Git executable (e.g., `C:\Program Files\Git\bin\git.exe`).
   - Click "Apply" or "OK" to save the settings.

6. Create and sign commits:
   - Open your project in PyCharm.
   - Make changes to your code.
   - Commit the changes using the Git interface in PyCharm.
   - In the commit dialog, check the "Sign commit" option.
   - Provide your GPG passphrase when prompted.

Your commit will now be signed with your GPG key. You can verify the signed commit on GitHub by looking for the "Verified" label on the commit.
