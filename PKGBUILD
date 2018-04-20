# Script generated with Bloom
pkgdesc="ROS - 3D models of the RH-P12-RN for simulation and visualization"
url='http://wiki.ros.org/rh_p12_rn_description'

pkgname='ros-kinetic-rh-p12-rn-description'
pkgver='0.1.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-joint-state-publisher'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=rh_p12_rn_description
source=()
md5sums=()

prepare() {
    cp -R $startdir/rh_p12_rn_description $srcdir/rh_p12_rn_description
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

