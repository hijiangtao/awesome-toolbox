## macOS

### 应用

* Xcode <https://apps.apple.com/us/app/xcode/id497799835?mt=12>
* 微信
* 企业微信
* Notion

### 开发环境

homebrew

```
// homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

// iTerm2
brew install --cask iterm2

// vscode
// 登陆同步配置
brew install --cask visual-studio-code

// chrome
// 登陆同步配置
brew install --cask chrome-remote-desktop-host

// git
brew install git

// nvm
// 需要进一步配置 https://github.com/nvm-sh/nvm
brew install nvm
nvm install node

// ssh key
ssh-keygen -t ed25519 -C "hijiangtao@gmail.com"
```

终端

```
// oh-my-zsh
// 文档 https://github.com/ohmyzsh/ohmyzsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

// ~/.zshrc 文件修改
// oh-my-zsh theme 设定主题 ZSH_THEME="agnoster"

// 安装 powerline-fonts 字体
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts

// iTerm 2 选定主题 Solarized Dark
// 修改透明度
```

### 配置

TBD
