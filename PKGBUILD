# Maintainer: Mike Yuan <me@yhndnzj.com>

pkgname=systemd-cleanup-pacman-hook-git
pkgver=git
pkgrel=1
pkgdesc="Pacman hook to stop and disable systemd units before removing packages"
arch=('any')
url="https://github.com/YHNdnzj/systemd-cleanup-pacman-hook"
license=('MIT')
makedepends=('git')
provides=('systemd-cleanup-pacman-hook')
conflicts=('systemd-cleanup-pacman-hook')
source=(
    "systemd-cleanup.hook"
    "systemd-cleanup"
    "README.md"
)
sha256sums=('SKIP'
            'SKIP'
            'SKIP')

pkgver() {
    git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

package() {
    depends=('bash' 'systemd')

    install -Dm644 systemd-cleanup.hook "$pkgdir/usr/share/libalpm/hooks/systemd-cleanup.hook"
    install -Dm755 systemd-cleanup "$pkgdir/usr/share/libalpm/scripts/systemd-cleanup"

    install -Dm644 README.md "$pkgdir/usr/share/doc/systemd-cleanup-pacman-hook/README.md"
}

# vim: set ts=4 sw=4 et:
