# Script generated with Bloom
pkgdesc="ROS - This is a programming framework to facilitate application development involving robot swarms. It makes coding for swarms much easier by providing an adequate swarm-level abstraction, as well as tools for swarm management, various communication mechanisms and so on. It also provides essential data structures, such as Neighbor, Swarm, and Virtual Stigmergy, to the user. Most importantly, it is completely compatible with ROS Indigo and presented in the form of a C++ library, which means that all resources in the ROS ecosystem are still available to the user. It is currently extensible to Opensplice DDS."
url='http://wiki.ros.org/micros_swarm_framework'

pkgname='ros-kinetic-micros-swarm-framework'
pkgver='0.0.17_3'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-app-loader'
'ros-kinetic-app1'
'ros-kinetic-app2'
'ros-kinetic-app3'
'ros-kinetic-gsdf-msgs'
'ros-kinetic-micros-swarm'
'ros-kinetic-micros-swarm-gazebo'
'ros-kinetic-micros-swarm-stage'
'ros-kinetic-olfati-saber-flocking'
'ros-kinetic-opensplice-dds-broker'
'ros-kinetic-pso'
'ros-kinetic-ros-broker'
'ros-kinetic-testbb'
'ros-kinetic-testnc'
'ros-kinetic-testrth'
'ros-kinetic-testscdspso'
'ros-kinetic-testvstig'
)

conflicts=()
replaces=()

_dir=micros_swarm_framework
source=()
md5sums=()

prepare() {
    cp -R $startdir/micros_swarm_framework $srcdir/micros_swarm_framework
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

