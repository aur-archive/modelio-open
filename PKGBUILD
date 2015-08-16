# Maintainer: Fabien Wang <fabienwang[at]eliteheberg[dot]fr>
pkgname=modelio-open
pkgver=3.3.1
pkgrel=1
pkgdesc="An open source UML tool that supports the UML2 and BPMN2 standards."
url="http://www.modelio.org/"
arch=('i686' 'x86_64')
license=('GPL3' 'APACHE')
depends=('glibc' 'gcc-libs' 'atk' 'cairo' 'gtk2' 'glib2' 'libwebkit' 'libxtst' 'webkitgtk2' 'java-runtime')
makedepends=()
conflicts=()
replaces=()
backup=()

_pkg_build_timestamp='201502191121'
source_i686=("http://downloads.sourceforge.net/modeliouml/${pkgname}-${_pkg_build_timestamp}-linux.gtk.x86.tar.gz")
source_x86_64=("http://downloads.sourceforge.net/modeliouml/${pkgname}-${_pkg_build_timestamp}-linux.gtk.x86_64.tar.gz")
source=('modelio.desktop')
md5sums_i686=('905991494f1c69cf1b49cba0d0c3051e')
md5sums_x86_64=('e51ea93be3f9147fb0c418d35273496e')
md5sums=('812c04e1dd64a06788c1595058317226')
options=(!strip)

prepare() {
  # rearrange the sources to prepare a "/opt"-friendly version
  mkdir -p ${srcdir}/opt
  mv ${srcdir}/Modelio\ 3.3 ${srcdir}/opt/${pkgname}
  # prepare the icon
  mkdir -p ${srcdir}/usr/share/icons
  cd ${srcdir}/usr/share/icons
  ln -s ../../../opt/${pkgname}/modelio.xpm
  # prepare the desktop file
  mkdir -p ${srcdir}/usr/share/applications
  cp ${srcdir}/modelio.desktop ${srcdir}/usr/share/applications/
}

package() {
  # copy the /opt and /usr directories for packaging
  cp -r ${srcdir}/opt ${pkgdir}/
  cp -r ${srcdir}/usr ${pkgdir}/
}

