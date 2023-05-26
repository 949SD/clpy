# Maintainer: David K david.dk949@gmail.com
_pkgname=clpy
pkgname="${_pkgname}-949sd"
pkgver=unknown
pkgrel=0
pkgdesc="A wrapper for python allowing it to be used like awk or sed."
arch=('any')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
depends=('python>=3.5')
provides=("clpy")
source=("$pkgname::git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make -j
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
