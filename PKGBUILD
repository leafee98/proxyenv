pkgname='proxyenv-git'
pkgver=0
pkgrel=1
arch=('any')
url="https://git.leafee98.com/leafee98/proxyenv"
pkgdesc="A cross-platform, GPU-accelerated terminal emulator"
license=('MIT')
depends=('bash')

source=(
    "proxyenv"
    "proxyenv.conf"
    "LICENSE"
)

sha256sums=(
    'SKIP'
    'SKIP'
    'SKIP'
)

pkgver() {
    git describe --tags --long  | cut -c 2- | sed -e 's/-/./g'
}

package() {
    install -Dm755 "${srcdir}/proxyenv" "${pkgdir}/usr/bin/proxyenv"
    install -Dm644 "${srcdir}/proxyenv.conf" "${pkgdir}/etc/proxyenv.conf"
    install -Dm644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/proxyenv/LICENSE"
}
