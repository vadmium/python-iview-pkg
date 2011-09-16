pkgname=iview
_proj="python-$pkgname"
_revno=69
pkgver="$_revno+0.2"  # Version number from iview.config.version
pkgrel=vad0
pkgdesc="Alternative frontend for the ABC TV's Iview service"
url="https://jeremy.visser.name/2009/08/$_proj"
arch=(any)
license=(GPL3)
makedepends=(bzr python2)
depends=(python2 python-beautifulsoup rtmpdump)
provides=("$_proj")
_loc="https+urllib://jeremy.visser.name/bzr/$_proj"
source=(python2.diff)
md5sums=(674dc19eb9c7a2a23bde17a9f2874c58)

build() {
    cd "$srcdir"
    
    if test -d "$_proj"; then
        cd "$_proj"
        bzr pull "$_loc" --revision "$_revno"
    else
        bzr branch "$_loc" --revision "$_revno" "$_proj"
        cd "$_proj"
    fi
    
    patch -p0 < ../python2.diff
}

package() {
    cd "$srcdir/$_proj"
    python2 setup.py install --root="$pkgdir" --optimize=1
}
