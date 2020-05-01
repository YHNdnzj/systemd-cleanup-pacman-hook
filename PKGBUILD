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
    "LICENSE"
)
sha256sums=('dee6825301d045f4e8ca8bd0ec07a00c89939f16d0c986ea96dc2a5e107ab9e1'
            '1efa7d1a7fe8a15d3bf72b8bb20086b7a2cdbb838ffbfe7cb5acae28eb3dc500'
            'b7d63c0afc21c2e21c2ef3cfa7fbd1f12b42da568831bcf24de5c56c7f065d63'
            '9d98f571d3683e2d771b8aa1eb23041c4d073de222ed2d054690e3366d97526a')

pkgver() {
    git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

package() {
    depends=('findutils' 'systemd')

    install -Dm644 systemd-cleanup.hook "$pkgdir/usr/share/libalpm/hooks/systemd-cleanup.hook"
    install -Dm755 systemd-cleanup "$pkgdir/usr/share/libalpm/scripts/systemd-cleanup"

    install -Dm644 README.md "$pkgdir/usr/share/doc/systemd-cleanup-pacman-hook/README.md"
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/systemd-cleanup-pacman-hook/LICENSE"
}

# vim: set ts=4 sw=4 et:
