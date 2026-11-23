# Maintainer: Ibrahim Rafi <rafiibrahim8 at hotmail dot com>

pkgname=csess-bin
_pkgname=csess
pkgver=0.1.0
pkgrel=1
pkgdesc="List, fork and move Claude Code sessions between directories (prebuilt binary)"
arch=('x86_64')
url="https://github.com/rafiibrahim8/csess"
license=('MIT')
depends=() # static, pure-Go binary
optdepends=('claude-code: the Claude Code CLI whose sessions this manages')
provides=("${_pkgname}")
conflicts=("${_pkgname}")
options=(!strip !debug) # release builds are already stripped (-s -w)
source=("${_pkgname}-${pkgver}-linux-x86_64.tar.gz::${url}/releases/download/v${pkgver}/${_pkgname}-v${pkgver}-linux-x86_64.tar.gz")
sha256sums=('ffec60411a1fa1fcf15701808eb6693cc4366c7341b5b6287dcf85a971424cb7')

package() {
  cd "${_pkgname}-v${pkgver}-linux-x86_64"

  install -Dm755 csess "${pkgdir}/usr/bin/csess"

  install -Dm644 man/csess.1 -t "${pkgdir}/usr/share/man/man1/"
  install -Dm644 completions/csess.bash "${pkgdir}/usr/share/bash-completion/completions/csess"
  install -Dm644 completions/_csess "${pkgdir}/usr/share/zsh/site-functions/_csess"
  install -Dm644 completions/csess.fish "${pkgdir}/usr/share/fish/vendor_completions.d/csess.fish"

  install -Dm644 README.md "${pkgdir}/usr/share/doc/${_pkgname}/README.md"
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
