### .bashrc example

```
alias onelogin-aws-login="docker run -v $HOME:/root -i -t koid/awscli-with-onelogin onelogin-aws-login $@"
alias aws="docker run -v $HOME:/root koid/awscli-with-onelogin aws $@"
```
