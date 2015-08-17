# Maintainer:  sudokode <sudokode@gmail.com>
# Contributor: Sven-Hendrik Haase <sh@lutzhaase.com>
# Contributor: grimi <grimi at poczta dot fm>

pkgname=urbanterror41-bin
pkgver=4.1.1
pkgrel=3
pkgdesc="A team-based tactical shooter based on the Quake 3 Engine (4.1 with data)"
arch=('i686' 'x86_64')
url="http://www.urbanterror.info"
license=('GPL2')
depends=('sdl' 'openal' 'curl')
makedepends=('mesa')
conflicts=('urbanterror41' 'urbanterror41-data')

# The binaries downloaded are official fixes for the troublesome clients that come in the official zip.
# You can check the files/checksums at http://www.urbanterror.info/downloads/security/#1.2
# They cannot be downloaded via makepkg because of how the download page works and will not fit in the source package.
# The Urban Terror mirrors are at the bottom. Uncomment one of the others if the mirror is down or slow.
source=("urbanterror.sh"
        "urbanterror-server.sh"
        "urbanterror.desktop"
        "urbanterror.png"
        "http://filebin.ca/P2FIDM515Qq/ioUrbanTerror.x86_64"
        "http://filebin.ca/P2FUhej6ep2/ioUrbanTerror.i386"
        "http://www.iourt.com/files/UrbanTerror411.zip")
        #"http://urbanterror.mtc-team.fr/UrbanTerror411.zip")
        #"http://clanurt.es/descargas/UrbanTerror411.zip")

md5sums=('ddb0480e6b48acbd776133aaed47278e'
         '264b4a4e0b9e02de829c256e0232fe36'
         '08a99f4d7ad63024bc886e118ddcbc0f'
         'f9a57d898df73f43c6a85c8d8cc455ba'
         '6b6712a02d904fae7a26cff3301ac2a4'
         '47dbd95cc65d796a83fb16301803a24d'
         '722c1fea9936593c9ef039bb068cc33b')

package() {
  install -d "$pkgdir"/opt/urbanterror41

  [[ $CARCH == "i686" ]] && install -m755 ioUrbanTerror.i386 "$pkgdir"/opt/urbanterror41/urbanterror
  [[ $CARCH == "i686" ]] && install -m755 UrbanTerror/ioUrTded.i386 "$pkgdir"/opt/urbanterror41/urbanterror-ded
  [[ $CARCH == "x86_64" ]] && install -m755 ioUrbanTerror.x86_64 "$pkgdir"/opt/urbanterror41/urbanterror
  [[ $CARCH == "x86_64" ]] && install -m755 UrbanTerror/ioUrTded.x86_64 "$pkgdir"/opt/urbanterror41/urbanterror-ded

  install -Dm644 urbanterror.desktop "$pkgdir"/usr/share/applications/urbanterror41.desktop
  install -Dm644 urbanterror.png "$pkgdir"/usr/share/pixmaps/urbanterror41.png

  install -Dm755 urbanterror.sh "$pkgdir"/usr/bin/urbanterror41
  install -Dm755 urbanterror-server.sh "$pkgdir"/usr/bin/urbanterror41-server

  cd UrbanTerror/q3ut4

  mkdir -p "$pkgdir"/opt/urbanterror41/q3ut4
  cp *.{txt,cfg} "$pkgdir"/opt/urbanterror41
  cp *.pk3 "$pkgdir"/opt/urbanterror41/q3ut4

  install -Dm644 readme41.txt "$pkgdir"/usr/share/licenses/urbanterror41/LICENSE
}

# vim: sw=2:ts=2 et:
