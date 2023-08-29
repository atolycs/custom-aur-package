# Maintainer: Atolycs
pkgname=aurutils-base
pkgver=1.0.0
pkgrel=1
pkgdesc="AURutils base directory setup meta package"
arch=("any") # 'any' or architecha
url="https://github.com/atolycs"
license=('MIT')
depends=('aurutils' 'pacman-contrib')
#optdepends=('')
#backup=('')
install=create-repo-db.install
source=("repo-config.conf" "create-repo-db.install")
sha256sums=('027dbd10aaac93501dc43d27f66def9404418028a3ccab02a8ae472d2c675e80'
            '7cc4dee8a52d056c30d3180975c74a47b5c807fa7fa20bb16f0f38149962c3c2')


package() {
   install -d "$pkgdir/var/cache/pacman/local_repo" 
   install -Dm0644 "${srcdir}/repo-config.conf" "$pkgdir/etc/pacman.d/local_repo/repo-config.conf"
}

