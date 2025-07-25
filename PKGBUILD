# Maintainer: arti
# Maintainer: redtide <redtid3@gmail.com>
# Contributor: Stefan Tatschner <stefan@rumpelsepp.org>

pkgname=wdisplays
pkgver=1.1.2
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
sha512sums=('cac7b9462f77ef448d9dfb47ce81b07b561cee64abaa667bd71d29632d92c82b3519125f14696c2fdf70ef247bd6e08e8f33d25c9794cf9cad6b6c8d4a202600')
b2sums=('eae2686e65b0f9ba2e91139804b131d367394fb3eae8506ee82d467b5b4daf87fba756bc7def51c0bbc0d796407b742241722897baf8072ed69d833701d19f1c')

build() {
  cd "$pkgname-$pkgver"
  arch-meson "$srcdir/build"
  ninja -C "$srcdir/build"
}

package() {
  cd "$pkgname-$pkgver"
  DESTDIR="$pkgdir" ninja -C "$srcdir/build" install
}
