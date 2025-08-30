1. Open your terminal app on your local machine
2. Type or paste in the following (substituting your own email)
`$ ssh-keygen -t ed25519 -C "your_email@example.com"`
This creates a new SSH key, using your email address as a label. 
3. When you’re prompted to supply a filename for the key, you can press **enter** to select the default. However if you have an existing key we suggest you name this new key manually. Remember to include the full path in they key name so that your key is saved in the right directory (typically `/Users/your_username/.ssh/`)
4. {% pill title="Optional" color="yellow" /%} You can add a passphrase if you prefer. Be sure to take note of the passphrase if you do set one. If you leave this blank then no passphrase will be set. 
5. Press enter to complete the process

You will now have an SSH key pair named `id_ed25519` and `id_ed25519.pub`. 