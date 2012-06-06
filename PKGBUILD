pkgname=iview
_proj="python-$pkgname"
_revno=71
pkgver="$_revno+0.2"  # Version number from iview.config.version
pkgrel=vad0
pkgdesc="Alternative frontend for ABC TV's Iview service"
url="https://jeremy.visser.name/2009/08/$_proj"
arch=(any)
license=(GPL3)
makedepends=(bzr python2 patch)
depends=(python2 python-beautifulsoup rtmpdump)
optdepends=("socksipy: Proxy support")
provides=("$_proj")
_loc="https+urllib://jeremy.visser.name/bzr/$_proj"
source=(setup.diff)
md5sums=(b907abcbfc89349b4871e61839732946)

build() {
    cd "$srcdir"
    
    if test -d "$_proj"; then
        cd "$_proj"
        bzr revert
        bzr pull "$_loc" --revision "$_revno"
    else
        bzr branch "$_loc" --revision "$_revno" "$_proj"
        cd "$_proj"
    fi
    
    patch -p0 < ../setup.diff
}

package() {
    cd "$srcdir/$_proj"
    python2 setup.py install --root="$pkgdir" --optimize=1
}
