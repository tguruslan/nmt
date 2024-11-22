# Maintainer: Ruslan Lopushan <tguruslan[at]udpu[dot]edu[dot]ua>
# Contributor: Ruslan Lopushan

pkgname=nmt
pkgver=3.0
pkgrel=1
arch=('any')
url="http://192.168.100.10/root/nmt"
_branch=main
license=('GPL')
pkgdesc='nmt'
depends=('pacman' 'google-chrome' 'rsync')
conflicts=('firefox' 'manjaro-hello')
makedepends=('git')
source=("git+$url.git#branch=$_branch")
sha256sums=('SKIP')

pkgver() {
    date +%Y%m%d
}

package() {
    install -d "$pkgdir/etc"
    install -d "$pkgdir/root"
    install -d "$pkgdir/usr"
    rsync -a "$srcdir/nmt/etc/" "$pkgdir/etc"
    rsync -a "$srcdir/nmt/root/" "$pkgdir/root"
    rsync -a "$srcdir/nmt/usr/" "$pkgdir/usr"
    chmod -R -w "$pkgdir/etc/opt/chrome/policies"
    chmod 750 "$pkgdir/root"
    chmod 700 "$pkgdir/root/.ssh"
    chmod +x "$pkgdir/etc/xdg/autostart/nmt.desktop"
    chmod +x "$pkgdir/etc/skel/Стільниця/nmt.desktop"
}
