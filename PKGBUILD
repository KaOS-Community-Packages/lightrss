pkgname=lightrss
pkgver=0.3.1
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
    '3f2862dc3f4a549b03c7c50d91cbcd8e7b57d4f8ced1df090c9b029f4e8f3ed7'
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
