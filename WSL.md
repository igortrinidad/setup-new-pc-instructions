# Setup new pc using WSL (Linux Ubuntu)

### General
```sh

git config --global user.email "@gmail.com"
git config --global user.name "Igor Trindade"
git config --global init.defaultBranch main
git config --global pull.rebase false

sudo apt update

# After copying the old ssh keys to backward compability
chmod 600 ~/.ssh/id_rsa
chmod 700 ~/.ssh

# On each repository
git init
git remote add origin [:git url]
git pull
git checkou main --force


```

### Install Docker
```sh
sudo apt update

sudo apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker ${USER}
su - ${USER}
groups
sudo usermod -aG docker [username]
```

### Install Node using nvm
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
source ~/.bashrc
```

### Install Chromium browser (Puppeteer and Scrappers)
```sh
sudo apt install chromium-browser
sudo apt install ca-certificates fonts-liberation libatk-bridge2.0-0 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgbm1 libgcc1 libglib2.0-0 libgtk-3-0 libnspr4 libnss3 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 lsb-release wget xdg-utils
# Puppeteer WSL specific dependencies
sudo apt install libgtk-3-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2
```

### Go lang

```sh
wget https://go.dev/dl/go1.24.7.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.24.7.linux-amd64.tar.gz

export PATH=$PATH:/usr/local/go/bin
source ~/.bashrc
go version

sudo apt-get update && sudo apt-get install -y --no-install-recommends \
    ca-certificates \
    netcat-openbsd \
    postgresql-client \
    openssl \
    curl \
    ffmpeg \
    tzdata
```


### Install Homebrew
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```