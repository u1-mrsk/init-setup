# Initial Setup on Ubuntu 18.04 LTS

## Settings on gnome desktop and system key binding
    $ gsettings set org.gnome.desktop.interface gtk-key-theme Emacs
    $ gsettings set org.gnome.desktop.input-sources xkb-options "['ctrl:nocaps']"
    $ gsettings set org.gnome.desktop.interface clock-show-date true
    $ gsettings set org.gnome.nautilus.desktop trash-icon-visible false

    $ LANG=C xdg-user-dirs-gtk-update

## Settings on dev-packages
    $ sudo apt update
    $ sudo apt upgrade -y

    $ sudo apt install -y build-essential
    $ sudo apt install -y libgtk-3-dev libtiff5-dev libgif-dev libjpeg-dev \
                          libpng-dev libxpm-dev libncurses5-dev libffi-dev \
                          libbz2-dev libreadline-dev libsqlite3-dev \
                          libssl-dev libgnutls28-dev libcurl4-openssl-dev
    $ sudo apt install -y gdebi-core
    $ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
    $ sudo dpkg -i google-chrome-stable_current_amd64.deb

## Settings on Git and dot-configuration files
    $ sudo apt install -y git-all

    $ git clone https://github.com/u1-mrsk/dot-conf.git
    $ ln -sf dot-conf/vimrc ~/.vimrc
    $ ln -sf dot-conf/vim ~/.vim
    $ ln -sf dot-conf/profile ~/.profile
    $ ln -sf dot-conf/bashrc ~/.bashrc
    $ ln -sf dot-conf/gitconfig ~/.gitconfig

## Settings on Vim
    $ sudo apt install -y vim

## Settings on Python
    $ sudo apt install -y python3
    $ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
    $ source ~/.profile
    $ pyenv install --list
    $ pyenv install 2.7.16
    $ pyenv install 3.7.3
    $ pyenv global 3.7.3
    $ pip install --upgrade pip

## Settings on Rust
    $ sudo apt install -y curl
    $ sudo apt install -y mingw-w64
    $ curl https://sh.rustup.rs -sSf | sh
    $ source ~/.profile
    $ ln -sf ~/dot-conf/cargo_config ~/.cargo/config
    // and when executing later
        $ rustup target add x86_64-pc-windows-gnu
        $ cargo build --release --target=x86_64-pc-windows-gnu --verbose


