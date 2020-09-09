## ProGuard's performance problem during migration from 6.0.3 to 6.2.2

### Possible params:
proguard-runtime.version = 6.0.3, 6.2.2

proguard-conf = proguard.conf, proguard_with_keep.conf

### Example:

`mvn clean package -Dproguard-runtime.version=6.0.3 -Dproguard-conf=proguard.conf`
 
`mvn clean package -Dproguard-runtime.version=6.2.2 -Dproguard-conf=proguard_with_keep.conf`

### Result is seconds:
````
__________________________________________
|proguard-runtime.version ||       |       | 
|proguard-conf            || 6.0.3 | 6.2.2 | 
|=========================||===============|
|                         ||       |       |
|proguard.conf            || 3.5s  | 4.2s  |
|_________________________||_______|_______|
|                         ||       |       |
|proguard_with_keep.conf  ||  5s   | 19.6s |  <-- !
|_________________________||_______|_______|
                                     
                                      ^
                                      |
                                ~4-5 times slowly 
````