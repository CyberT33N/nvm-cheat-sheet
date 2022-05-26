# nvm-cheat-sheet (https://github.com/nvm-sh/nvm)
NVM cheat sheet with the most needed stuff

<br><br>

# Install
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```





















<br><br>
_________________________________________________
_________________________________________________
<br><br>

## Install specific Node version
```bash
nvm install 12.16.1
```













<br><br>
_________________________________________________
_________________________________________________
<br><br>

## Use specific Node Version
```bash
nvm use 16
```











<br><br>
_________________________________________________
_________________________________________________
<br><br>


## Set default version (https://stackoverflow.com/questions/47190861/how-can-the-default-node-version-be-set-using-nvm)
```bash
nvm alias default v10.19.0

nvm alias default v18
```


























<br><br>
_________________________________________________
_________________________________________________
<br><br>

# Dockerfile
```bash
# Install node
ENV NODE_VERSION 14
ENV NVM_DIR /usr/local/nvm
RUN mkdir -p $NVM_DIR && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash && \
    . $NVM_DIR/nvm.sh && \
    nvm alias default $NODE_VERSION && \
    nvm use default && \
    ln -s $NVM_DIR/versions/node/$(nvm run node --version | tail -1)/bin /node_bin
ENV NODE_PATH $NVM_DIR/lib/node_modules
ENV PATH /node_bin:$PATH

RUN node --version && exit
```

