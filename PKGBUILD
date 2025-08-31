pkgname=gdbm
pkgver=1.26
pkgrel=2
pkgdesc="GNU database library"
arch=('x86_64')
url="https://www.gnu.org/software/gdbm/"
license=('GPL-3.0-or-later')
depends=(
    'bash'
    'glibc'
)
makedepends=('readline')
source=(https://ftp.gnu.org/gnu/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(6a24504a14de4a744103dcb936be976df6fbe88ccff26065e54c1c47946f4a5e)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        --disable-static
        --enable-libgdbm-compat
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
