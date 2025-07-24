# Lab 4 Survival guide.

1. Clone this repo

```bash
git clone
```

2. ใน terminal รันคำสั่งนี้ 

``` bash
docker-compose up -d
```

3. ตรวจสอบชื่อ container service
```bash 
docker-compose ps
```
จะเห็นชื่อ service จากตัวอย่างคือ `esp32-dev`


4. เข้าไปใน container ด้วยคำสั่ง

```bash
docker-compose exec -it esp32-dev bash
```

5. export environment variables
```bash
. $IDF_PATH/export.sh
```

6. สร้าง project
```bash
idf.py create-project -p Hello_World Hello_World
```


7. แก้ไข code ใน main.c

```c
#include <stdio.h>

void app_main(void)
{
    int i = 1;
    while(1)
    {
        printf("Hello World %d\r\n",i);
        i++;
    }
}
```

8. build project

```bash
cd Hello_World
idf.py build
```

9. simulate

```bash
idf.py qemu monitor
```

10. stop emulator

กด `ctrl+]`