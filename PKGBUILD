pkgname=iview  # TODO: python-iview
_rev=c4220ab
pkgver="351+g$_rev"  # Commit count: git rev-list --count "$_rev"
pkgrel=1
pkgdesc="Alternative frontend for ABC TV's Iview service"
url="https://github.com/vadmium/python-iview"
arch=(any)
license=(GPL3)
makedepends=(python3)
depends=(python3)
optdepends=(
    "python-socks: Proxy support"
    "python-gobject: GTK frontend"
    "gtk3: GTK frontend"
    "rtmpdump: News 24 live stream"
)
provides=(python-iview)

source=("https://github.com/vadmium/python-iview/tarball/$_rev")
md5sums=(04d8248f027742d135651944fd056680)

package() {
    cd "$srcdir/vadmium-python-iview-$_rev"
    python3 setup.py install --root="$pkgdir" --optimize=1
}
