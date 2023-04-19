# Install

## Ubuntu

    % cat /etc/os-release

    NAME="Ubuntu"
    VERSION="20.04.6 LTS (Focal Fossa)"
    ID=ubuntu

## ブログにて

NeoVimでの、Pythonのコード補完の為に設定した記録を残しました。

- [NeoVim Ubuntuへインストール・設定してみた](https://blog.tstylestudio.com/2023/02/18/neovim-ubuntu%e3%81%b8%e3%82%a4%e3%83%b3%e3%82%b9%e3%83%88%e3%83%bc%e3%83%ab%e3%83%bb%e8%a8%ad%e5%ae%9a%e3%81%97%e3%81%a6%e3%81%bf%e3%81%9f/)
- [NeoVim設定-コード補完機能追加 Deno, Dein.div, dcc.vim](https://blog.tstylestudio.com/2023/04/13/neovim%e8%a8%ad%e5%ae%9a-%e3%82%b3%e3%83%bc%e3%83%89%e8%a3%9c%e5%ae%8c/)


### NeoVim

aptでインストールされるバージョンは古いバージョンなので、最近のをインストールするために**snap**を使う。

    sudo apt remove neovim
    sudo snap install nvim --classic

### Nodejs

(偶数バージョンがおすすめ)
coc.vimで必要になるのでインストールする

    curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\
    sudo apt-get install -y nodejs

### coc.nvim

- 必要に応じて追加(追記)していく
- **coc.nvim**はパッケージマネージャーで追加する
- LSPをフルサポートしたプラグイン
- node.js 必須

私のdein.tomlファイルのcoc.nvimの設定はこちらから拝借いたしました。ありがとうございます。

- [第11回 Neovimのすゝめ – LSPをセットアップ（coc編）](https://wonwon-eater.com/nvim-susume-lsp-coc/)

#### LSP Language Server Protocol

- プログラミング言語の構文解析・構文ハイライト・静的エラーチェック・リファレンス参照・入力補完といった機能


#### ripgrep

- [高速で便利なgrep「ripgrep」を活用する](https://gihyo.jp/admin/serial/01/ubuntu-recipe/0579)

「Error on "..": spawn rg ENOENT」と出る場合は**ripgrep**をインストールする

    sudo snap install ripgrep --classic


### Font

フォルダやファイルのTreeを左に出す時のアイコン用のFontをインストール

    mkdir ~/.local/share/fonts
    cd ~/.local/share/fonts

(1行で入力)

    curl -fLo "Droid Sans Mono for Powerline Nerd Font Complete.otf" https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/complete/Droid%20Sans%20Mono%20Nerd%20Font%20Complete.otf

## プラグインのインストール

NeoVimを再起動する毎に、新しく設定したプラグインはインストールされる。
