# Script generated with Bloom
pkgdesc="ROS - rqt_pr2_dashboard is a GUI for debugging and controlling low-level state of the PR2. It shows things like battery status and breaker states, as well as integrating tools like rqt_console and robot_monitor."
url='http://ros.org/wiki/rqt_pr2_dashboard'

pkgname='ros-kinetic-rqt-pr2-dashboard'
pkgver='0.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-diagnostic-msgs'
'ros-kinetic-pr2-msgs'
'ros-kinetic-pr2-power-board'
'ros-kinetic-roslib'
'ros-kinetic-rospy'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-py'
'ros-kinetic-rqt-robot-dashboard'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
)

conflicts=()
replaces=()

_dir=rqt_pr2_dashboard
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_pr2_dashboard $srcdir/rqt_pr2_dashboard
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

