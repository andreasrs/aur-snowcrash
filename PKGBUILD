# Maintainer: Andreas Rudi Søvik <arsovik@gmail.com>
pkgname=snowcrash
pkgver=0.11.0
pkgrel=1
epoch=
pkgdesc="snowcrash - API Blueprint Parser"
arch=('any')
url="https://github.com/andreasrs/snowcrash"
license=('MIT')
makedepends=('git python2')
options=()
install=
changelog=
source=('git+https://github.com/apiaryio/snowcrash.git' 'make.patch')
md5sums=('SKIP' '6ae6f52348f133b49f02869bb07c3c97')

build() {
	cd "${srcdir}"/${pkgname}
    git checkout v$pkgver
	git submodule init
	git submodule update
	patch -p0 < $srcdir/make.patch
	python2 configure
	make test
}

package() {
	mkdir -p "$pkgdir/usr/bin"
	cd snowcrash
	make DESTDIR="$pkgdir/usr/bin" install
}

