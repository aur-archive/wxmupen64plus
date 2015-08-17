# Maintainer: BeholdMyGlory <larvid@gmail.com>
pkgname=wxmupen64plus
pkgver=0.3
_pkgrev=0564db396383
pkgrel=4
pkgdesc="A full-featured frontend for Mupen64Plus written using wxWidgets"
arch=('i686' 'x86_64')
url="https://bitbucket.org/auria/wxmupen64plus"
license=('GPL')
depends=('sdl' 'wxgtk2.9')
makedepends=('mupen64plus' 'python')
install="wxmupen64plus.install"
source=(https://bitbucket.org/auria/wxmupen64plus/get/${pkgver}.tar.gz wxmupen64plus.desktop wscript.patch)
md5sums=('c3d5e8a19e6c6aaa1fa6478b522bbd58' 'abe57a02b9366b63b83967f94bc3dc5c' 'e5a7eac3db5df39189b107c64eb95575')

build() {
  cd "$srcdir/auria-wxmupen64plus-${_pkgrev}"

  patch -p0 < "${srcdir}/wscript.patch"

  ./waf --mupenapi="/usr/include/mupen64plus" --wxconfig="/usr/bin/wx-config-2.9" --libdir="/usr/lib" --prefix="${pkgdir}/usr" configure
  ./waf
  ./waf install

  install -Dm644 "${srcdir}/wxmupen64plus.desktop" "${pkgdir}/usr/share/applications/wxmupen64plus.desktop"
}
