## Installing python-pcl
Use the release 1.8.1 instead of dev `git checkout pcl-1.8.1`  
Note to modify line 10 in /usr/local/lib/pkgconfig/pcl_features-1.8.pc for 
`fetal error: pcl/point_cloud.h: No such file or directory`
```
Requires: pcl_common-1.8 pcl_search-1.8 pcl_kdtree-1.8 pcl_octree-1.8 pcl_filters-1.8 #pcl_2d-1.8
```
## Upgrade pip
After `pip install --upgrade pip` to upgrade to version 18.1, then it will meet problem `ImportError: cannot import name main`. To solve this open the file with `sudo kate /usr/bin/pip` and change the lines
```python
from pip import main
if __name__ == '__main__':
    sys.exit(main())
```
to
```python
from pip import __main__
if __name__ == '__main__':
    sys.exit(__main__._main())
```
