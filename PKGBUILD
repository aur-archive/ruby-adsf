# Maintainer: Jeremy "Ichimonji10" Audet <ichimonji10 at gmail dot com>
# Contributor: carlf <carlf at photocarl dot org>
# Contributor: oslik <oslik at mail dot ru>
#
# namcap warns that dependency ruby-rack is an unnecessary dependency. This is
# untrue.

pkgname=ruby-adsf
_pkgname="${pkgname#ruby-}"
pkgver=1.2.0
pkgrel=3
pkgdesc='A tiny web server that you can launch instantly in any directory.'
arch=(any)
url='http://stoneship.org/software/adsf/'
license=(MIT)
depends=(ruby-rack)
makedepends=(rubygems)
options=(!emptydirs)
source=("https://rubygems.org/downloads/${_pkgname}-${pkgver}.gem")
noextract=("${_pkgname}-${pkgver}.gem")
sha256sums=('a92d7310c3c27418ee5f6126df9cd20a95d3e4c277c1f7f24a4cc7102e720b62')

package() {
  # install gem
  HOME=/tmp gem install \
    --no-user-install \
    --ignore-dependencies \
    --install-dir "${pkgdir}$(ruby -rubygems -e 'puts Gem.default_dir')" \
    --bindir "${pkgdir}/usr/bin" \
    "${srcdir}/${_pkgname}-${pkgver}.gem"

  # install license
  install -Dm 644 \
    "${pkgdir}"/usr/lib/ruby/gems/*/gems/"${_pkgname}-${pkgver}"/LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set ts=2 sw=2 et:
