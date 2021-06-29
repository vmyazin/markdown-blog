# Run Tapirio with Node and Yarn on Mac locally

make sure that using bash, if not change to it

    chsh -s /bin/bash

## Download and install Node
https://nodejs.org/en/download/

it will ask to make sure that /usr/local/bin in the $PATH
on macos it is in /etc/paths file (most likely it is there)

## Install Yarn
Yarn suggest to install using npm

    npm install --global yarn

if you get errors, the following helped:
but it might give an error about permission - Missing write access to /usr/local/lib/node_modules

    sudo chown -R $USER /usr/local/lib/node_modules

the to avoid next set of errors run:

    mkdir ~/.npm-global
    npm config set prefix '~/.npm-global'
    export PATH=~/.npm-global/bin:$PATH
    touch ~/.bash_profile
    source ~/.bash_profile

than again

    npm install --global yarn

check yarn version with

    yarn --version


## Tapirio
Clone tapirio locally with Git

    git clone https://github.com/vmyazin/tapirio.git
    cd tapirio
    mv content/preferences-default.json content/preferences.json

Then when Tapirio site is cloned in git, switch to that directory,

    yarn 
    yarn start
    
than go to http://localhost:3001

