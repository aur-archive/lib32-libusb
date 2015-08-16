# Maintainer: Maxime Gauduin <alucryd@archlinux.org>
# Maintainer: 3V0LU710N <db_eee@hotmail.com>

pkgname=lib32-libusb
pkgver=1.0.19
pkgrel=1
pkgdesc='A cross-platform user library to access USB devices'
arch=('x86_64')
url='http://libusb.info/'
license=('LGPL')
depends=('lib32-systemd' 'libusb')
replaces=('lib32-libusb1' 'lib32-libusbx')
provides=('lib32-libusbx')
makedepends=('gcc-multilib')
source=("http://downloads.sourceforge.net/libusb/libusb-${pkgver}.tar.bz2")
sha256sums=('6c502c816002f90d4f76050a6429c3a7e0d84204222cbff2dce95dd773ba6840')

build() {
  cd libusb-${pkgver}

  export CC='gcc -m32'
  export CXX='g++ -m32'
  export PKG_CONFIG_PATH='/usr/lib32/pkgconfig'

  ./configure \
    --prefix='/usr' \
    --libdir='/usr/lib32' \
    --disable-static
  make
}

package () {
  cd libusb-${pkgver}

  make DESTDIR="${pkgdir}" install
  rm -rf "${pkgdir}"/usr/include
}

# vim: ts=2 sw=2 et:
