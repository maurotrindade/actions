## Solution
Use ssh keys and define host aliases in ssh config file (each alias for an account).

2. Edit/Create ssh config file (`~/.ssh/config`):

   ```conf
   # Default github account: oanhnn
   Host github.com
      HostName github.com
      IdentityFile ~/.ssh/oanhnn_private_key
      IdentitiesOnly yes
      
   # Other github account: superman
   Host github-superman
      HostName github.com
      IdentityFile ~/.ssh/superman_private_key
      IdentitiesOnly yes
   ```
   
   > NOTE: If you use any account frequently, you should use the default hostname (`github.com`).
   
3. [Add ssh private keys to your agent](https://help.github.com/articles/adding-a-new-ssh-key-to-the-ssh-agent/):

   ```shell
   $ ssh-add ~/.ssh/oanhnn_private_key
   $ ssh-add ~/.ssh/superman_private_key
   ```

4. Test your connection

   ```shell
   $ ssh-keyscan github.com >> ~/.ssh/known_hosts
   $ ssh -T git@github.com
   $ ssh -T git@github-superman
   ```

   If everything is OK, you will see these messages:

   ```shell
   Hi oanhnn! You've successfully authenticated, but GitHub does not provide shell access.
   ```
   
   ```shell
   Hi superman! You've successfully authenticated, but GitHub does not provide shell access.
   ```

5. Now all are set, you need remeber 

   ```
   git@github-superman:org/project.git => user is superman
   git@github.com:org/project.git.     => user is oanhnn
   ```

  - If you need clone a repository, just do:

   ```shell
   $ git clone git@github-superman:org1/project1.git /path/to/project1
   $ cd /path/to/project1
   $ git config user.email "superman@example.com"
   $ git config user.name  "Super Man"
   ```

   - If you already have the repo set up, after the ssh config instructions, you need change the URL of `origin`, just do:

   ```
   $ git remote set-url origin git@github-superman:org2/project2.git
   $ git config user.email "superman@example.com"
   $ git config user.name  "Super Man"
   ```

   - If you are creating a new repository on local:

   ```
   $ cd /path/to/project3
   $ git init
   $ git remote add origin git@github-superman:org3/project3.git
   $ git config user.email "superman@example.com"
   $ git config user.name  "Super Man"
   ```
