# Paper Pool for Network Theory Group

This is a repository for storing files of various papers. Because of possible copyright issues, we decide to make this repository private instead of public. You can go to [the corresponding website](https://network-theory-group.github.io/) to get the details of these papers.


## How to Upload Papers to This Repo

+ If you do not have a personal GitHub account and you want to use this account (i.e., account `network-theory-group`)
    + Clone this repo: `git clone https://github.com/network-theory-group/paper-pool.git`
    + Copy the papers you want to upload
    + Upload:
      ```bash
      git add -A
      git commit -am "add some papers"
      git push origin master
      ```
     Note that the message after `git commit -am` can be an arbitrary nessage.
+ If you already have a personal GitHub account and you want to use both of the two accounts(i.e., your personal account and account `network-theory-group`), one possible solution is to use SSH
    + First, you need to create a SSH key, [here](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) is a tutorial
    + Then, upload the SSH key to GitHub, [here](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) is a tutorial
    + If you want to use SSH to manage both of the accounts, you need do some configurations for your SSH (If you use HTTP to manage one and SSH to manage the other, then you do not need the following configurations)
        + Add the following to your `~/.ssh/conf` (if you donot have the file, then create it)
          ```
          Host github-ntg
              HostName github.com
              User git
            IdentityFile </path/to/your/ssh-key>
          ```
          Note that, you need to change `</path/to/your/ssh-key>' to the location of the corresponding SSH private key, for example, `/home/saber/.ssh/ntg`. Noet also you need to create different SSH keys for different GitHub accounts and this solution can support arbitrary number of GitHub accounts.
    + Now you can play with both of the accounts (assuming that Host `github-ntg`)
        + Clone: `git clone git@github-ntg:network-theory-group/paper-pool.git`
        + Upload: the same as before



## Potential Ideas

### Application Oriented

+ [ ] String match (assuming symbol frequency non-uniform)
    + random permutation (mapping each symbol to an integer in [N], where N is the number of different symbols)
        + using counter for differences as a fingerprint
        + using reverse order counter as a fingerprint
        + building fingerprint by slicing the original string intro peaces (support approximate substring matching)
    
+ [ ] Use EEC to assist near-duplicates detection
    + Using `simHash` to generate a 1024 byte (or some other reasonable length) long fingerprint
    + Using EEC to encode the fingerprint and save the encoded values into an array of bucks 
    + For the new document to be detected, first generate its fingerprint and encoding using EEC and search against the bucks

