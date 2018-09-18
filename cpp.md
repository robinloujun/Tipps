## timers

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

```
#include <ctime>
clock_t start, diff;
start = clock();
diff = clock() - start;
std::cout << ((float)diff)/CLOCKS_PER_SEC << " s." << std::endl;
```
