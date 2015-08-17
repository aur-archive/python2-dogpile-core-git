# Maintainer: Anthony Cornehl <accornehl@gmail.com>
# https://github.com/twinshadow/openstack-aur

_realpkgname="dogpile-core"
pkgname="python2-${_realpkgname}-git"
pkgdesc="A lock which allows a single thread to hold a resource while allowing many readers."
pkgver=0.0.0
pkgrel=2
conflicts=("python2-${_realpkgname}")
provides=("python2-${_realpkgname}")
arch=("any")
license=("custom")
url="https://bitbucket.org/zzzeek/dogpile.core"
depends=(
    "python2"
)
makedepends=(
    "python2-setuptools"
    "git"
)
source=("$pkgname"::"git+https://bitbucket.org/zzzeek/${_realpkgname//-/.}.git")
md5sums=("SKIP")

pkgver() {
  cd "$pkgname"
  local ver="$(git describe --long)"
  printf "%s" "${ver//-/.}"
}

build() {
  cd "$pkgname"
  python2 setup.py build
}

package() {
  cd "$pkgname"
  python2 setup.py install --root="$pkgdir" --optimize=1
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/${_realpkgname}/LICENSE"
}
