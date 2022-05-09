First-time Setup

 This will setup and configure git and GitHub on your own VM or Matrix. Run everything as your local user, unless indicated otherwise.

 1. Configure git with your full name and Seneca e-mail address:

    git config --global user.name "Firstname Lastname"
    git config --global user.email "yoursenecaid@myseneca.ca"

 2. You may want to add a key to Github to reduce password prompts. Generate an SSH key-pair to add to your GitHub account:

    ssh-keygen #Follow defaults (hit enter)
    cat ~/.ssh/id_rsa.pub

3. Copy/paste your public key from above (starting from ‘ssh-rsa’) to your GitHub account in this link:

    https://www.github.com/settings/ssh/new

4. Create ops445 directory within your home directory:

    mv ~/ops445 ~/old_ops445 #ONLY IF you have an exisiting ops445 directory, rename it first:
    mkdir ~/ops445

Per-Lab Setup

This will download Lab 1 locally, allowing you to work on your scripts and upload (push) them back up to GitHub.

 5. Clone your lab repository into your ~/ops435/lab1 directory using SSH:

    git clone git@github.com:OPS445/lab1-yourgithubusername.git ~/ops445/lab1/
    cp ~/old_ops445/lab1/lab1?.py ~/ops445/lab1/ #ONLY IF YOU HAVE CREATED PYTHON FILES 

Submission (if the lab is completed)

6. Run the checking script. Make sure you identify and correct any and all errors in your scripts:

    cd ~/ops435/lab1/
    pwd #confirm that you are in the right directory
    python3 ./CheckLab1.py -f -v

7. Create lab1_yoursenecaid.txt by redirecting the output from CheckLab1.py:

    python3 ./CheckLab1.py -f -v &> lab1_yoursenecaid.txt

8. Commit and push (upload) your lab work:

    git add lab1*
    git commit -m "Adding Lab1 files"
    git push 

You can make changes to your scripts and reupload as many times as you like. Make sure you commit and push to do so.

Note: Your lab is automatically submitted at the due date and time using the last published code. Any changes you publish after the due date won't be marked or seen by your professor.
