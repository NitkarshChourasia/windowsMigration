# Use documentation by github far better then this, respectively.


Certainly! To add GPG to GitHub and have verified signed commits, you can follow these steps:

1. Generate a GPG key pair:
   - Open a terminal or command prompt on your Windows 10 machine.
   - Run the command: `gpg --full-generate-key`
   - Follow the prompts to select the key type, key size, expiration date, and enter your name and email address.

2. List your GPG keys:
   - Run the command: `gpg --list-secret-keys --keyid-format LONG`
   - Locate the key ID associated with the key you generated. It will be displayed in the output and will start with "sec" (e.g., sec rsa4096/XXXXXXXXXXXXXXXX).

3. Configure Git to use your GPG key:
   - Run the command: `git config --global user.signingkey <key ID>`
   - Replace `<key ID>` with the actual key ID you noted down in the previous step.

4. Export your GPG public key:
   - Run the command: `gpg --armor --export <key ID>`
   - Replace `<key ID>` with the actual key ID you noted down earlier.
   - Copy the entire output of the command, starting from "-----BEGIN PGP PUBLIC KEY BLOCK-----" and ending with "-----END PGP PUBLIC KEY BLOCK-----".

5. Add the GPG key to your GitHub account:
   - Go to the GitHub website (github.com) and log in to your account.
   - Click on your profile picture in the top-right corner and select "Settings" from the dropdown menu.
   - In the left sidebar, click on "SSH and GPG keys".
   - Click on the "New GPG key" button.
   - Paste the GPG key you copied from the previous step into the "Key" field.
   - Click on the "Add GPG key" button.
   - GitHub will validate and add your GPG key to your account.

6. Configure Git to sign commits by default:
   - Run the command: `git config --global commit.gpgsign true`

Now, when you make commits using Git and push them to GitHub, they will be signed with your GPG key. GitHub will show the commits as verified, indicating that they were signed by you.

Note: Make sure you have Git and GPG installed on your Windows 10 machine before following these steps.

I hope this helps! Let me know if you have any further questions.


If you want to configure Git to cache your GPG passphrase indefinitely, you can set the cache timeout value to a very large number. Here's how you can do it:

1. Open a command prompt or Git Bash.

2. Set Git to use the credential manager by running the following command:
   ```
   git config --global credential.helper manager
   ```

3. Configure the cache timeout for the credential manager. Set the timeout value to a large number, such as 9999999, to effectively make it cache the passphrase indefinitely. Run the following command:
   ```
   git config --global credential.helper 'cache --timeout=9999999'
   ```

4. With this configuration, Git will cache your GPG passphrase indefinitely, and you won't be prompted for it again for subsequent signed commits.

Keep in mind that by setting the cache timeout to a very large number or infinity, the cached passphrase will remain stored in memory for an extended period. This can be convenient for your workflow, but it's important to consider the security implications, especially if you're working in a shared or public environment.
