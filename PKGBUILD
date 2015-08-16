# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-menus
pkgver=1.6.0
pkgrel=3
pkgdesc="MATE menu specifications"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('glib2' 'python2')
makedepends=('gobject-introspection'  'mate-common' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('798e1e96e8dea48d93f1db90b6fbe69d0a3f3ea5')

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    PYTHON=/usr/bin/python2 ./autogen.sh \
        --prefix=/usr \
        --sysconfdir=/etc \
        --localstatedir=/var \
        --enable-python \
        --disable-static
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
