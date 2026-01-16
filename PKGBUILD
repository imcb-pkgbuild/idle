# Maintainer: imcb <irismessage@protonmail.com>

pkgname='idle'
pkgver=3.11
pkgrel=2
pkgdesc='Python Integrated Development and Learning Environment (desktop entry)'
arch=('any')
url='https://packages.debian.org/stable/python/idle'
license=('PSF-2.0')
groups=()
depends=(
    'python'
    'tk'
    'hicolor-icon-theme'
)
optdepends=()
makedepends=()
provides=(
    'idle3'
    'python-idle'
)
conflicts=()
replaces=()
source=(
    'idle.desktop'
    'idle.1'
)
sha256sums=('1e8c56ac32b2376da4221cd94b3f255b20d27977b593373808f664c0b968697f'
            '79fb08b181f6744905b231aca17d283c80d0434f25b25355825eb2120c7e8e91')

package() {
    install -D -m644 -t "${pkgdir}/usr/share/applications" ${pkgname}.desktop
    install -D -m644 -t "${pkgdir}/usr/share/man/man1" ${pkgname}.1

    for _icon in 16 32 48 256; do
        _icon_dir="${pkgdir}/usr/share/icons/hicolor/${_icon}x${_icon}/apps"
        install -d "${_icon_dir}"
        ln -s "/usr/lib/python${pkgver}/idlelib/Icons/idle_${_icon}.png" "${_icon_dir}/${pkgname}.png"
    done
}
