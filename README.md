# my-osx-settings
My OSX Settings

### Setting

##### Show access modifier for classes in IntelliJ
* https://stackoverflow.com/questions/45369257/how-to-show-access-modifiers-for-classes-in-intellij-idea
* -Dide.projectView.show.visibility=true

##### Convert '₩' to '\`'
* https://ani2life.com/wp/?p=1753
* https://gist.github.com/redism/43bc51cab62269fa97a220a7bb5e1103

##### Use ⌥ ← and ⌥→ to jump forwards/backwards words in iTerm 2, on OS X
* https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x

### brew
```
brew install awscli
brew install aws-elasticbeanstalk

brew install wget
brew install httpstat

brew install jenv
brew install scalaenv

brew install rbenv
brew install ruby-build

brew install nodenv
brew install node-build

brew install pyenv
brew install pyenv-virtualenv
brew install autoenv
```

### brew cask
```
brew cask install alfred

brew cask install jetbrains-toolbox
brew cask install sublime-text
brew cask install sourcetree
brew cask install iterm2

brew cask install docker

brew cask install 1password
brew cask install authy

brew cask install dropbox
brew cask install slack

brew cask install google-chrome
brew cask install postman
```

### App Store
```
Line
KakaoTalk

Airmail 3
Reeder 3

Status Clock
Weather Wall
```

### Menually
```
Dynamon
```

### .bash_profile
```
PS1="\u@\h \w $ "

export TERM=xterm-color
export CLICOLOR=1
export LSCOLORS=ExFxCxDxBxegedabagacad
export GREP_OPTIONS='--color=auto'
export GOPATH=/usr/local/go
export HISTTIMEFORMAT="%y/%m/%d %T "

alias ls='ls -GFh'
alias ll='ls -l'
alias la='ls -la'

function ssh-aws-ec2user() { ssh -i ~/.ssh/xxx.pem ec2-user@"$1"; }
alias as=ssh-aws-ec2user

function git-pull-all() {
    START=$(git symbolic-ref --short -q HEAD);
    for branch in $(git branch | sed 's/^.//'); do
        git checkout $branch;
        git pull ${1:-origin} $branch || break;
    done;
    git checkout $START;
};

function git-push-all() {
    git push --all ${1:-origin};
};

# Env Series
eval "$(jenv init -)"
eval "$(rbenv init -)"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
source $(brew --prefix autoenv)/activate.sh
eval "$(scalaenv init -)"
eval "$(nodenv init -)"
```
