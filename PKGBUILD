pkgname=lightrss
pkgver=0.4
pkgrel=1
pkgdesc="A simple qt based rss feed reader"
url="https://github.com/deussomniat/${pkgname}"
license=('GPL')
arch=('x86_64')
depends=('qt5-base')
makedepends=('make')
source=(
    "${url}/archive/v${pkgver}.tar.gz"
    'catalog.xml'
)
sha256sums=(
    'c017d9d1c4eb8390112afddc96e636a0e5f177270f6c76e7db93f5c5fde51307'
    '88e6d4f4977742ff3f7c4cdf0bf1534322a9ab89b2dbb999e5a7760fcc27f417'
)

prepare() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    cp -f "${srcdir}/catalog.xml" "${srcdir}/${pkgname}-${pkgver}/resources"
    /usr/lib/qt5/bin/qmake
}

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    install -Dm755 "${srcdir}/${pkgname}-${pkgver}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
    install -Dm644 "${srcdir}/${pkgname}-${pkgver}/resources/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
    install -Dm644 "${srcdir}/${pkgname}-${pkgver}/images/${pkgname}.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/${pkgname}.png"
}
