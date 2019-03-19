pkgname=lightrss
pkgver=0.3
pkgrel=1
pkgdesc="A simple qt based rss feed reader"
url="https://github.com/deussomniat/${pkgname}"
license=('GPL')
arch=('x86_64')
depends=('qt5-base')
makedepends=('make')
source=(
    "${url}/archive/v${pkgver}.tar.gz"
    'lightrss.desktop'
)
sha256sums=(
    '5d932e86a059a092462bb3195860cffc80ee5f683e968bea3edde76114078ae3'
    '48922e5c467ca65c1b6cbdbe84782f2256852ed0db72307ca946febcee97ecca'
)

prepare() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    /usr/lib/qt5/bin/qmake
}

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    install -Dm755 "${srcdir}/${pkgname}-${pkgver}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
    install -Dm644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
    install -Dm644 "${srcdir}/${pkgname}-${pkgver}/images/rss48.png" "${pkgdir}/usr/share/icons/hicolor/48x48/apps/${pkgname}.png"
}
