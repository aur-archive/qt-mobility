# Submitter: Perry3D
# Maintainer: Maciek <maciekwer at wp dot pl>
# Contributor: giniu
pkgname=qt-mobility
pkgver=1.2.0
pkgrel=3
pkgdesc="It is a project within Nokia that is creating a new suite of Qt APIs for mobile device functionality. These APIs will enable cross-platform mobile application development."
arch=('x86_64' 'i686')
url="http://qt.nokia.com"
license=('LGPL')
depends=('qt>=4.7' 'bluez')
makedepends=('perl')
optdepends=('networkmanager: Bearer Management'
            'tracker: Document Gallery'
            'gstreamer0.10-plugins>=0.10.19: Multimedia mediaservice plugins')
source=(http://get.qt.nokia.com/qt/add-ons/$pkgname-opensource-src-$pkgver.tar.gz)
md5sums=('ea5db5a8d3dd4709c2926dceda646bd8')

build() {
  cd "$srcdir/${pkgname}-opensource-src-${pkgver}"

  ./configure -prefix /usr \
    -plugindir /usr/lib/qt/plugins \
    -silent

  make
}

package() {
  cd "$srcdir/${pkgname}-opensource-src-${pkgver}"

  make INSTALL_ROOT="$pkgdir/" install
  
  install -d ${pkgdir}/usr/share/doc/qt
  cp -r doc/qch ${pkgdir}/usr/share/doc/qt/
}

# vim:set ts=2 sw=2 et:
