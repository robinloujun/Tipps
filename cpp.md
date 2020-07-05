## To Do

- [ ] summarize the error: undefined reference to '...'

## timers
can also see the [blog text](https://blog.csdn.net/zxxSsdsd/article/details/14481627)

#### time_t & difftime in ctime.h
Problem is that the unit is only second
```
#include <ctime>
time_t start, finish;
time(&start);
...
time(&finish);
std::cout << difftime(finish, start) << " s." << std::endl;
```
#### clock_t in ctime.h
diff_time with higher accuracy 
```
#include <ctime>
clock_t start, diff;
start = clock();
diff = clock() - start;
std::cout << ((float)diff)/CLOCKS_PER_SEC << " s." << std::endl;
```

#### error: undefined reference to '...'
[refer](https://blog.csdn.net/cserchen/article/details/5503556)


## Compiling pcl from source with Anaconda
pcl=1.9.1 vtk=8.2.0
when facing problem like error 
```shell
error: /usr/lib/../lib64/libSM.so: undefined reference to `uuid_generate@UUID_1.0'
```
ccmake and modify the Qt5 relative source from Anaconda to `/opt/Qt5.11.2/5.11.2/gcc_64/lib/cmake/` (check the version before modification)
