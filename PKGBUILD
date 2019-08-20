# Maintainer: Ricardo Grim Cabrita <grimkriegor@krutt.org>

pkgname=kotlin-language-server
pkgver=0.3.0
_commit=6ccc0bea196a88b242b90fe87477cb978d46d7ef
pkgrel=1
pkgdesc="Smart code completion, diagnostics and more for Kotlin using the Language Server Protocol"
arch=(any)
url="https://github.com/fwcd/KotlinLanguageServer.git"
license=('MIT')
conflicts=('kotlin-language-server-git')
provides=('kotlin-language-server')
depends=('java-runtime')
makedepends=('git')
source=("${pkgname}::git+https://github.com/fwcd/KotlinLanguageServer.git#commit=$_commit")
sha256sums=('SKIP')

build() {
    cd "${srcdir}/${pkgname}"
    ./gradlew server:installDist
}

package() {
    mkdir -p \
      "${pkgdir}/usr/share/kotlin" \
      "${pkgdir}/usr/bin"
    cp -r \
      "${srcdir}/${pkgname}/server/build/install/server/" \
      "${pkgdir}/usr/share/kotlin/kotlin-language-server"
    ln -srf \
      "${pkgdir}/usr/share/kotlin/kotlin-language-server/bin/kotlin-language-server" \
      "${pkgdir}/usr/bin/kotlin-language-server"
}

