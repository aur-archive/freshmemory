# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=freshmemory
pkgver=1.1.1
pkgrel=1
pkgdesc="A learning tool using the Spaced Repetition method."
arch=(i686 x86_64)
url="http://freshmemory.sourceforge.net/"
license=('GPL3')
depends=('qt4' 'shared-mime-info')
backup=("etc/xdg/$pkgname/$pkgname.ini")
install="$pkgname.install"
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname/$pkgver/$pkgname-$pkgver.tar.bz2")
md5sums=('b6dc526d1a2bbd154c89fa42f038d395')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  # do not run debian postinst and fix mime path
  sed -e "/mime.path/s/$pkgname/mime\/application/" \
      -e "/postinst/d" -i $pkgname.pro

  qmake-qt4 && make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make INSTALL_ROOT="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
