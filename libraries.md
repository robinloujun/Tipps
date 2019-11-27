# Libraries

### Eigen
Download a released version from [Eigen Wiki](http://eigen.tuxfamily.org/index.php?title=Main_Page#Download), the source code are maintained in [Bitbucket](https://bitbucket.org/eigen/eigen/src/default/).

```shell
cd {$eigen_path}
mkdir build
cd build
cmake ..
sudo make install
cd /usr/local/include
sudo ln -sf eigen3/Eigen Eigen
sudo ln -sf eigen3/unsupported unsupported
```
