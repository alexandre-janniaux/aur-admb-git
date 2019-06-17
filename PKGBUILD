# Maintainer : Alexandre Janniaux <alexandre+aur@janniaux.me>
pkgname=admb-git
pkgdesc="ADMB is a statistical application that implements AD using C++ classes and a native template language."
pkgver=r4936.20447721
pkgrel=1
arch=('x86_64')
license=('BSD')
url="https://github.com/DigitalPulseSoftware/NazaraEngine"
source=("git+https://github.com/admb-project/admb.git")
depends=()
optdepends=()
makedepends=('git')
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
noextract=()
validpgpkeys=()
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/admb"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/admb/"
	make
}

package() {
	cd "$srcdir/admb/"
	mkdir -p "$pkgdir/usr/bin/" "$pkgdir/usr/lib/"
	install -D admb "$pkgdir/usr/bin/"
	install -D build/dist/lib/libadmb-contribo.so "$pkgdir/usr/lib/"
	install -D build/dist/lib/libadmb-contrib.so "$pkgdir/usr/lib/"
	install -D build/dist/lib/libadmbo.so "$pkgdir/usr/lib/"
	install -D build/dist/lib/libadmb.so "$pkgdir/usr/lib/"
}
