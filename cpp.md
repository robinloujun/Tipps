## timers

### difftime in ctime.h
Problem is that the unit is only second
```
#include <ctime>
time_t start, finish;
time(&start);
...
time(&finish);
std::cout << difftime(finish, start) << std::endl;
```
