# Maintainer: Reventlov <contact@volcanis.me>

pkgname=jumanji
pkgver=963b309
pkgrel=2
pkgdesc="a web browser"
arch=('i686' 'x86_64')
url="http://pwmt.org/projects/jumanji"
license=('custom')
depends=('girara' 'webkitgtk' 'libsoup>=2.36.1' 'sqlite3')
makedepends=('git')
conflicts=('jumanji-git' 'jumanji-new_webgtk-git' 'jumanji-raedwulf-git')
provides=('jumanji')
source=('jumanji::git+git://pwmt.org/jumanji.git')
md5sums=('SKIP')
_repo=jumanji

build() {
  cd "$srcdir/$_repo"

  CFLAGS+=" -O0" make
}

package() {
  cd "$srcdir/$_repo"

  make DESTDIR="$pkgdir/" install
  install -D -m664 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

pkgver() {
  cd "$srcdir/$_repo"

  local ver="$(git describe --always --long)"
  printf "%s" "${ver//-/.}"
}

# vim:set ts=2 sw=2 et:
