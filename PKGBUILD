# Maintainer: arti
# Maintainer: redtide <redtid3@gmail.com>
# Contributor: Stefan Tatschner <stefan@rumpelsepp.org>

pkgname=wdisplays
pkgver=1.1.1
pkgrel=1
pkgdesc="GUI display configurator for wlroots compositors"
url="https://github.com/artizirk/wdisplays"
license=(GPL3)
arch=(x86_64)
depends=(
  gtk3
  libepoxy
  wayland
  wayland-protocols
)
makedepends=(
  meson
)
source=(
  $pkgname-$pkgver.tar.gz::$url/archive/$pkgver.tar.gz
)
sha512sums=(
  '46923592e9fbb5c06c3549c198aedbafd8e0b5a6a82bc11d9d0b4cb0860070000cce18e0aa109932a4e4bee34d9f235660d2ea9d485a8fce146a2755ef62f81d'
)
b2sums=(
  'a294719c3b8e91642d53e22aaac40c3ddd9a24e2eaef8e8b412905e9a4ef4be7984c0d0c087661d975ec518304020d1f84fc7a6ac4f62f1a5708c73878646818'
)

build() {
  cd "$pkgname-$pkgver"
  arch-meson "$srcdir/build"
  ninja -C "$srcdir/build"
}

package() {
  cd "$pkgname-$pkgver"
  DESTDIR="$pkgdir" ninja -C "$srcdir/build" install
}
