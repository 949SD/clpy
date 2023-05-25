# Maintainer: David K david.dk949@gmail.com
pkgname=clpy
pkgver=v1.0.1
pkgrel=1
pkgdesc="A wrapper for python allowing it to be used like awk or sed."
arch=('any')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=('python>=3.5')
provides=("$pkgname")
source=("git+$url")
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
