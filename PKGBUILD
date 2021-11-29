#Maintainer Erik Inkinen <erik.inkinen@gmail.com>
pkgname=libgrilio
provides=('libgrilio')
_pkgbase=libgrilio
pkgver=146.6966247
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/sailfishos/libgrilio"
license=('BSD')
depends=('libglibutil')
makedepends=('git' 'pkgconfig')
source=("libgrilio::git+https://github.com/sailfishos/libgrilio.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib KEEP_SYMBOLS=1 release pkgconfig
}

package() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib DESTDIR="$pkgdir/" install-dev
}

