# Maintainer: Atolycs
pkgname=vscode-server
pkgver=1.80.0
pkgrel=1
pkgdesc="Official Visual Studio Code server"
arch=(x86_64) # 'any' or architecha
url="https://az764295.vo.msecnd.net/stable"
license=('')
depends=('tar' 'xz' 'curl')
#optdepends=('')
#backup=('')
__stable_hash=$(curl https://update.code.visualstudio.com/api/commits/stable/server-linux-x64-web | cut -d '"' -f 2)

source=("vscode-server.service")
source_x86_64=(
     "${url}/${__stable_hash}/vscode-server-linux-x64-web.tar.gz"
)
sha256sums=('b7f527ac6d720ccf04d6802df00c991bf3be036b70378893317918bcb24be063')
sha256sums_x86_64=('037f545da6d61c8b03c11df6660bb6e862fabccf89e3c19d47907f25fffbd216')

#build() {
#}

package() {
   mkdir -p "$pkgdir/opt"
   mv "vscode-server-linux-x64-web" "$pkgdir/opt/$pkgname"

   mkdir -p "$pkgdir/usr/bin"
   ln -s "/opt/$pkgname/bin/code-server" "$pkgdir/usr/bin/code-server"

   mkdir -p "$pkgdir/usr/lib/systemd/system"
   cp -aL "$pkgname.service" "$pkgdir/usr/lib/systemd/system/$pkgname.service"

   mkdir -p "$pkgdir/usr/share/licenses"
   cp -a "$pkgdir/opt/vscode-server/LICENSE" "$pkgdir/usr/share/licenses/$pkgname"
}

