# Maintainer: Aspen Schneider <rendezvous71@outlook.com>

pkgname='laniakea-dotnet-sdk'
pkgdesc='Laniakea SDK for .NET'
_pkgver=0.1.0
_dotnetmajor=9
_sdkminor=104
pkgver="${_pkgver}.sdk${_sdkminor}"
pkgrel=1
url='https://www.laniakeaos.com/'
arch=('any')
license=('MIT')
makedepends=(
)
depends=(
  dotnet-sdk
  laniakea-dotnet-runtime
)

validpgpkeys=(
  '425529067DE156F86814B55D2AE736768A7E87E6'
)

source=(
  "git+https://github.com/laniakeaos/Laniakea.NET.git#tag=v${_pkgver}"
)
b2sums=(
  'SKIP'
)


build() {
  echo "build..."
  cd $srcdir/Laniakea.NET
  make sdk
}

package() {
  cd $srcdir/Laniakea.NET
  make DESTDIR=$pkgdir DOTNET_SDK_VERSION="${_dotnetmajor}.0.${_sdkminor}" install-sdk
}
