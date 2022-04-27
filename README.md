# openeb_vendor

## Introduction

ROS 2 vendor package for [openeb](https://github.com/prophesee-ai/openeb)

## Building

Make sure you have sourced ROS 2 environment. If not, do

```
source /opt/ros/<replace your ROS 2 distro version here>/setup.sh
```

Then clone this repo, and check dependencies to make sure all depends library are installed.

```
mkdir -p evt_ws/src
cd evt_ws/src
git clone https://github.com/homalozoa/openeb_vendor.git
cd ..
rosdep install --from-paths src --ignore-src -r -y
```

Make sure all installations are succeed.

Then, just build this package with `colcon`

```
colcon build
```

or

```
colcon build --merge-install
```

## License

This is just a vendor package for [openeb](https://github.com/prophesee-ai/openeb), hince all copyright of source code in `openeb` is belong to its project. The license of this repo is `Apache License 2.0`.
