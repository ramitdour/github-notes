## SSH Key Generation

Only if accout is not linked 

Generating key locally , use same email add as of github account , run

`ssh-keygen -t rsa -b 4096 -C "ramit.dour@gmail.com"`

enter key file name :testkey
enter  pass phrase : hellogit
enter pass phrase : hello git

Now the key will be generated


run in terminal  to get keys
`ls | grep testkey`

`testkey` private key , keep it secure
`testkey.pub` public key that will be uploaded

`cat testkey.pub`

copy the key text and paste below

github settings >SSH and GPG keys > New SSH key > title > paste key


Now telling local git about private key , so it can communicate with github
i.e. 
##### Adding your SSH key to the ssh-agent

Add the new SSH key to the ssh-agent

The ssh-agent is another program that is part of the SSH toolsuite. The ssh-agent is responsible for holding private keys. Think of it like a keychain. In addition to holding private keys it also brokers requests to sign SSH requests with the private keys so that private keys are never passed around unsecurly.

Before adding the new SSH key to the ssh-agent first ensure the ssh-agent is running by executing:

```shell
eval "$(ssh-agent -s)"
```

Once the ssh-agent is running the following command will add the new SSH key to the local SSH agent.

```bash
ssh-add -K /Users/you/.ssh/id_rsa
```

The new SSH key is now registered and ready to use!

Resurces:

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

https://www.atlassian.com/git/tutorials/git-ssh