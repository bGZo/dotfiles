# dotfiles

在類 nix 系統中，大多數應用配置的存儲方式為純文本格式（Plain text）[^DOTFILES_INTRO]，如何在不同機器中獲得相同的開發體驗，這是一個重要的課題。如果你看過一些國外的開發者，一定會注意到他們有一些同名率相當高的倉庫，`dotfiles` 就是其中之一。

因為國內大環境已 Windows 為主，而商用 UNIX 門檻又很高（MacOS很貴），所以不接觸服務器的朋友很難瞭解這部分內容。拋卻功利性的目的，這部分相比 Windows 更具開放性和定製性，即使用來消遣時間也是個不錯的選擇。


## zsh

The construct of zsh is like this:

```bash
./zsh
|-- aliases
|-- bindkeys.zsh
|-- colors.zsh
|-- dircolors
|-- histories.zsh                 # history record rule
|-- options.zsh
|-- personalFunctions.zsh         # custom function
|-- prompt_purification_setup
|-- zsh-autosuggestions/          # submodule for complete by history
|-- zsh-syntax-highlighting/      # submodule for highlight
|-- zshenv                        # environment
`-- zstyles.zsh
```

>[!IMPORTENT]
Those softwares shouold be required:
```bash
$ sudo pacman -S zsh git
```

Git should be config like:

```bash
git config --global user.name 'HX'
git config --global user.email ''
ssh-keygen -t rsa -C ""
```

Clone repo, then:

```bash
$ git submodule update --init --recursive
$ git submodule update --remote --recursive 
$ cp zsh/.zshrcBackup ~/.zshrc
$ vim ~/.zshrc
$ chsh -s /usr/bin/zsh
```

## Scopes

- [x] zsh
- [x] samba
- [x] maven
- [x] logseq
- [ ] vscode

[^DOTFILES_INTRO]: https://www.freecodecamp.org/news/dotfiles-what-is-a-dot-file-and-how-to-create-it-in-mac-and-linux/
