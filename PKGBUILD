pkgname=slinktool
pkgver=4.2
pkgrel=4
epoch=
pkgdesc="Utility to access seismological data via SeedLink protocol. This package provides libslink as well."
arch=('i686' 'x86_64')
url="http://www.iris.edu/data/dmc-seedlink.htm"
license=('GPL' 'LGPL')
groups=()
depends=('glibc')
makedepends=()
checkdepends=()
optdepends=()
provides=('libslink-2.3')
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(http://www.iris.edu/pub/programs/SeedLink/$pkgname-$pkgver.tar.gz)
noextract=()
md5sums=('b9e0bdcf0df34087525da3f003ceb8dc')
sha256sums=('b411d5d699314978b9df717782d4c89a059923eae14c759be2c0eec89fa8b9ae')

build() {
  cd "$srcdir/$pkgname"
  make
  cd libslink
  make shared
}

package() {
  cd "$srcdir/$pkgname"

  install -Dm755 slinktool "${pkgdir}/usr/bin/slinktool"
  install -Dm644 doc/slinktool.1 "${pkgdir}/usr/share/man/man1/slinktool.1"
  install -Dm755 libslink/libslink.so.2.3 "${pkgdir}/usr/lib/libslink.so.2.3"
  ln -s /usr/lib/libslink.so.2.3 "${pkgdir}/usr/lib/libslink.so"
  install -Dm644 libslink/libslink.a "${pkgdir}/usr/include/libslink.a"
  install -Dm644 libslink/libslink.h "${pkgdir}/usr/include/libslink.h"
  install -Dm644 libslink/slplatform.h "${pkgdir}/usr/include/slplatform.h"
  install -dm755 "${pkgdir}/usr/share/man/man3/"
  install -Dm644 -t "${pkgdir}/usr/share/man/man3/" libslink/doc/*.3
}

# vim:set ts=2 sw=2 et:
