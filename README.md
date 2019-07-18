### Secrets


## Developer setup

Gopass (https://github.com/gopasspw/gopass) needs to be installed to access this repository. Gopass has some dependencies, follow these steps to install them.

## Pre-Installation Steps

gopass needs some external programs to work:
* `gpg` - GnuPG, preferably in Version 2 or later
* `git` - Git SCM, any Version should be OK

```bash
brew install gnupg2
```

#### Creating GPG keys using command line interface.

gopass depends on the gpg program for encryption and decryption. You must have a suitable key pair. To list your current keys, you can do:

```bash
gpg --list-secret-keys
```

If there is no output, then you don't have any keys. To create a new key:

```bash
gpg --full-generate-key
```


You will be presented with several options:

* Key type: Choose either "RSA and RSA" or "DSA and ElGamal".
* Key size: Choose at least 2048.
* Validity: 5 to 10 years is a good default.
* Enter your real name and primary email address.
* A comment is not necessary.
* Pass phrase: Make sure to pick a very long pass phrase, not just a simple password. Remember this should be stronger than any of the secrets you store in the password store. You can configure the GPG Agent later to save you repetitive typing.


Now, you have created a public and private key pair. If you don't know what that means, of if you are not familiar with GPG, it is highly recommend you do a little reading on the subject. Check out the following manuals:

* ["git + gpg, know thy commits" at coderwall](https://coderwall.com/p/d3uo3w/git-gpg-know-thy-commits)
* ["Generating a new GPG key" by GitHub](https://help.github.com/articles/generating-a-new-gpg-key/)


## Pre-Installation Steps

```bash
brew install gopass
```

If you're using a password on your gpg key, you also have to install pinentry-mac from brew and configure it in your ~/gpg/gpg-agent.conf

```
brew install pinentry-mac
echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf
```

## Post-Installation Steps

**Enable Bash Auto completion**

If you use Bash, you can run one of the following commands to enable auto completion for sub-commands like `gopass show`, `gopass ls` and others.

```bash
source <(gopass completion bash)
```

**UI for Gopass** 

There is [Gopass UI](https://github.com/codecentric/gopass-ui) which was exclusively implemented for gopass and is available for MacOS.


## Using go-pass

Once installed take some time to read through to understand how `gopass` works.
https://github.com/gopasspw/gopass/blob/master/docs/features.md
