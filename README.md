# comp9318 Assignment 1
#### student Name: *Kun Dong*
#### Student ID: *z5047518*

## Question 1
### (1) Table R

| cubeID        | Location      | Time  | Item | SUM(Quantity)|
| ------------- |:-------------:| -----:|-----:|-------------:|
| Location, Time, Item| Sydney | 2005| ps2| **1400**|
| Location, Time, Item| Sydney | 2006| ps2| **1500**|
| Location, Time, Item| Sydney | 2006| wii| **500**|
| Location, Time, Item| Melbourne | 2005| XBox 360| **1700**|
|  |  |  | | |
| Location, Item | Sydney | ALL| ps2| **2900**|
| Location, Item | Sydney | ALL| wii| **500**|
| Location, Item | Melbourne | ALL|  XBox 360| **1700**|
|  |  |  | | |
| Location, Time | Sydney | 2005| ALL| **1400**|
| Location, Time | Sydney | 2006| ALL| **2000**|
| Location, Time | Melbourne | 2005| ALL| **1700**|
|  |  |  | | |
| Time ,Item | ALL | 2005| ps2| **1400**|
| Time ,Item | ALL | 2006| ps2| **1500**|
| Time ,Item | ALL | 2006| wii| **500**|
| Time ,Item | ALL | 2005| XBox 360| **1700**|
|  |  |  | | |
| Location | Sydney | ALL| ALL| **2400**|
| Location | Melbourne | ALL| ALL| **1700**|
|  |  |  | | |
| Item | ALL | ALL| ps2| **2900**|
| Item | ALL | ALL| wii|  **500**|
| Item | ALL | ALL| XBox 360| **1700**|
|  |  |  | | |
| Time | ALL | 2005 | ALL| **3100**|
| Time | ALL | 2006 | ALL| **2000**|
|  |  |  | | |  
|  | ALL | ALL | ALL| **5100**|

### (2) standard SQL construct
```SQL
SELECT L, T, I, SUM(M) FROM R GROUP BY L, T, I UNION ALL
```
```SQL
SELECT L, ALL, I, SUM(M) FROM R GROUP BY L, I UNION ALL
```
```SQL
 SELECT L, ALL, I, SUM(M) FROM R GROUP BY L, I UNION ALL
```
```SQL
 SELECT L, T, ALL, SUM(M) FROM R GROUP BY L, T UNION ALL
 ```
```SQL
 SELECT ALL, T, I, SUM(M) FROM R GROUP BY T, I UNION ALL
 ```
```SQL
 SELECT L, ALL, ALL, SUM(M) FROM R GROUP BY L UNION ALL
 ```
```SQL
 SELECT ALL, ALL, I, SUM(M) FROM R GROUP BY I UNION ALL
 ```
```SQL
 SELECT ALL, T, ALL, SUM(M) FROM R GROUP BY T UNION ALL
 ```
```SQL
 SELECT ALL, ALL, ALL, SUM(M) FROM R
 ```
### (3) tabular form for
```SQL
SELECT Location, Time, Item, SUM(Quantity) FROM Sales CUBE BY Location, Time, Item HAVING COUNT(*) > 1
```
| cubeID        | Location      | Time  | Item | SUM(Quantity)|
| ------------- |:-------------:| -----:|-----:|-------------:|
| *Location, Time *| Sydney  | 2006 | ALL | 2000|
| *Location, Item *| Sydney  | ALL | PS2 | 2900|


