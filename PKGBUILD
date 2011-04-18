# Contributor: Daniel Mills <danielmills1@gmail.com>

pkgname=meat-git
pkgver=20110401
pkgrel=1
pkgdesc="Bash wrapper for Cower"
arch=('i686' 'x86_64')
url="http://github.com/e36freak/meat"
license=('MIT')
depends=('bash' 'cower' 'awk')
makedepends=('git')
optdepends=('sudo: get prompted less when installing'
            'pacman-color: colorized output')
_gitroot='http://github.com/e36freak/meat.git'
_gitname='meat'

build() {
  cd "$scrdir"
  msg "Connecting to GIT server...."

  if [[ -d $_gitname ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  cd "$_gitname"

  install -m 755 -D meat "$srcdir/pkg/usr/bin/meat"
}

# vim: ft=sh syn=sh et
