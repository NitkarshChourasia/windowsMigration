To sign commits in VS Code while committing to GitHub, you can follow these steps:

1. Install Git and GPG:
   Make sure Git and GPG are installed on your system. You can install them by running the following commands in the terminal:
   ```
   sudo apt install git
   sudo apt install gnupg
   ```

2. Generate a GPG key:
   Generate a GPG key using the following command:
   ```
   gpg --full-generate-key
   ```
   Follow the prompts and enter the necessary information.

3. Configure Git to use the GPG key:
   Configure Git to use the GPG key by running the following command:
   ```
   git config --global user.signingkey <GPG-key-id>
   ```
   Replace `<GPG-key-id>` with the key ID you generated in step 2.

4. Configure Git to sign all commits:
   Configure Git to sign all commits by running the following command:
   ```
   git config --global commit.gpgsign true
   ```

5. Configure VS Code to use Git:
   Open VS Code and go to the Command Palette (Ctrl+Shift+P on Windows or Command+Shift+P on macOS) and select "Git: Initialize Repository". Select the folder containing your project.

6. Commit your changes:
   Make your changes to the code and stage the changes using the Source Control panel in VS Code. When you are ready to commit, enter your commit message and select the "Sign off" checkbox.

That's it! Your commits will now be signed with your GPG key.
