# Maintainer: Nathan Fisher <nfisher dot sr gmail com>

pkgname=pekwm-menu-hg
pkgver=20130730
pkgrel=1
pkgdesc="Dynamic xdg menu creator for pekwm"
url="https://nfisher1226@bitbucket.org/nfisher1226/pekwm-menu"
arch=('i686' 'x86_64')
license=('GPL')
depends=('menu-cache' 'gtk2')
optdepends=('lxmenu-data: LXDE menus' 'gnome-menus: GNOME menus')
makedepends=('mercurial')
provides=('pekwm-menu')

_hgroot='https://nfisher.sr@code.google.com/p'
_hgrepo='pekwm-menu/'

build() {
cd $startdir/src

# Update the repo, else clone a new one
  if [ -d $_hgrepo ]; then
    cd $_hgrepo
    make clean
    hg pull -u
  else
    hg clone ${_hgroot}/${_hgrepo}
    cd $_hgrepo
  fi
  make
}

package() {
  cd $_hgrepo
  make install DESTDIR="${pkgdir}/usr/"
}
