# git-crypt-demo

https://github.com/AGWA/git-crypt

Prerequisites
Install Homebrew (macOS only)
Install GPG (on Linux, this is probably already installed; on macOS, brew install gpg)
Install git-crypt

## Linux
### Build git-crypt
git clone https://github.com/AGWA/git-crypt.git
cd /path/to/git-crypt
make
git-crypt --version should work - otherwise cp /path/to/git-crypt/git-crypt /usr/local/bin

### If you have Ubuntu-18
apt install -y git-crypt

## Mac OS X
brew install git-crypt

brew install gpg

#########################################################################################

## Encrypt files
cd /path/to/<my-repo>
  
git-crypt init

vi .gitattributes

Specify future files to encrypt in .gitattributes

<files-to-encrypt> filter=git-crypt diff=git-crypt
  
where <files-to-encrypt> follows the same syntax as files specified in .gitignore
  

Add files specified in .gitattributes to <my-repo> and push up to Git host
  
Verify in Git host files are encrypted


#########################################################################################

## GPG 
gpg --gen-key 

gpg --list-keys

git-crypt add-gpg-user "Paul Brennaman <paul.brennaman@outlook.com>"

git-crypt status

git-crypt status -f
