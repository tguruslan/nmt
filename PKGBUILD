# Maintainer: Ruslan Lopushan <tguruslan[at]udpu[dot]edu[dot]ua>
# Contributor: Ruslan Lopushan

pkgname=nmt
pkgver=3.0
pkgrel=1
arch=('any')
url="https://github.com/tguruslan/nmt"
_branch=main
license=('GPL')
pkgdesc='nmt'
depends=('pacman')
conflicts=('firefox' 'manjaro-hello')
makedepends=('git')
source=("git+$url.git#branch=$_branch")
sha256sums=('SKIP')

pkgver() {
    date +%Y%m%d
}

package() {
    depends+=('google-chrome' 'rsync')
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
