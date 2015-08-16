# Contributor: ponsfoot <cabezon dot hashimoto at gmail dot com>
# Contributor: philacs

_pkgname=libvisio
pkgname=${_pkgname}-git
pkgver=930.a59d35d
pkgrel=1
pkgdesc="A library providing ability to interpret and import visio diagrams"
arch=('i686' 'x86_64')
url="http://www.freedesktop.org/wiki/Software/libvisio"
license=('LGPL')
provides=('libvisio')
conflicts=('libvisio')
options=(!libtool)
depends=('libwpd>=0.9' 'libwpg>=0.2.0' 'libxml2' 'gperf>=3.0')
makedepends=('git' 'boost')
source=(git://anongit.freedesktop.org/libreoffice/contrib/libvisio)
sha1sums=('SKIP')

pkgver() {
  cd $_pkgname
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd $_pkgname
  ./autogen.sh
  ./configure --without-docs --enable-static=no --prefix=/usr
  make
}

package() {
  cd $_pkgname
  make DESTDIR="$pkgdir" install
}
