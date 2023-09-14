# Maintainer: Atolycs
pkgname=vscode-server
pkgver="1.82.1"
pkgrel=1
pkgdesc="Official Visual Studio Code server"
arch=(x86_64) # 'any' or architecha
url="https://az764295.vo.msecnd.net/stable"
license=('')
depends=('tar' 'xz' 'curl' 'jq')
#optdepends=('')
#backup=('')
__stable_hash=$(curl https://update.code.visualstudio.com/api/commits/stable/server-linux-x64-web | cut -d '"' -f 2)

source=("vscode-server.service")
source_x86_64=(
     "${url}/${__stable_hash}/vscode-server-linux-x64-web.tar.gz"
)
sha256sums=('b7f527ac6d720ccf04d6802df00c991bf3be036b70378893317918bcb24be063')
sha256sums_x86_64=('a0e5ad88eba91124d18d8532b066650b1c625f7508d250b1f1216aa8c375a103')

pkgver() {
  printf "%s" $(curl -s "https://api.github.com/repos/microsoft/vscode/releases" | jq '.[0].tag_name')
}

#build() {
#}

package() {
   mkdir -p "$pkgdir/opt"
   mv "vscode-server-linux-x64-web" "$pkgdir/opt/$pkgname"

   mkdir -p "$pkgdir/usr/bin"
   ln -s "/opt/$pkgname/bin/code-server" "$pkgdir/usr/bin/code-server"

   mkdir -p "$pkgdir/usr/lib/systemd/user"
   install -Dm644 "$pkgname.service" -t "$pkgdir/usr/lib/systemd/user/"

   mkdir -p "$pkgdir/usr/share/licenses"
   install -Dm644 "$pkgdir/opt/vscode-server/LICENSE" -t "$pkgdir/usr/share/licenses/"
}

