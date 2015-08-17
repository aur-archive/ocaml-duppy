# Maintainer: Charles E. Hawkins <charlesthehawk at yahoo dot com>
# Contributor: Thomas S Hatch <thatch45 at gmail dot com>
# Contributor: Luciano A. Ferrer <laferrer@gmail.com>
pkgname=ocaml-duppy
pkgver=0.5.1
pkgrel=1
arch=('i686' 'x86_64')
license=('GPL')
pkgdesc="An advanced scheduler for Ocaml programmers"
url="http://savonet.sourceforge.net/"
depends=('glibc')
makedepends=('ocaml' 'ocaml-findlib' 'ocaml-pcre')
options=('!strip')
source=("http://downloads.sourceforge.net/savonet/${pkgname}-${pkgver}.tar.gz")
md5sums=('66c6c1b289113f02c138ea18f532c89a')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr --disable-ldconf
  make all
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  mkdir -p ${pkgdir}$(ocamlfind printconf destdir)
  make OCAMLFIND_LDCONF=ignore \
    OCAMLFIND_DESTDIR=${pkgdir}$(ocamlfind printconf destdir) install
}
