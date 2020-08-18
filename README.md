# dotfiles
#+TITLE:dotfiles
* Welcome!
This contains everything I use to config my computer, minus a few things that contain passwords!
* How to setup
This is pretty easy! all you need is [[https://www.gnu.org/software/stow/][Gnu Stow]].
#+BEGIN_SRC shell
git clone --recursive https://github.com/flitbip/dotfiles ~/dotfiles
cd ~/dotfiles
stow emacs # or whatever you want to use!
#+END_SRC

You can easily remove them by running
#+BEGIN_SRC shell
stow -D emacs
#+END_SRC
* Special setup
** Emacs
You will also need [[https://github.com/hlissner/doom-emacs/tree/develop][Doom emacs]].
#+BEGIN_SRC shell
git clone https://github.com/hlissner/doom-emacs ~/.emacs.d -b develop
cd ~/.emacs.d
make quickstart
#+END_SRC
And also, make sure to install the fonts in dotfiles/emacs/.doom.d/fonts.tar.gz
**THESE WILL MAKE THE SAVE ICON LOOK LIKE A LIGATURE IN EMACS**
*** +mail
For my mail setup i have my offlineimap running (config included in repo), and
also have a .msmtprc in my home directory. You can see how to configure that [[https://wiki.archlinux.org/index.php/Msmtp][Here]]

** Offlineimap
You will need to create a python file called ~decrypt.py~ with a function
mailpasswd() that returns the password
** Rofi
You have to install `rofi-pass` for pass-store integration.

You can also install rofimoji for an emoji picker https://github.com/fdw/rofimoji
** Nixos
Nixos can't be stow'd, so my setup is configuration.nix is symlinked to
/etc/nixos/ and home.nix is a [[ https://github.com/rycee/home-manager ][home-manager]] thing which is symlinked to
\~/.config/nixpkgs
