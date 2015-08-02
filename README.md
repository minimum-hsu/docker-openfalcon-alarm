# docker-openfalcon-alarm

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-alarm .
```

## Run

### Basic Run

Use default configuration, and falcon-alarm package.

```
$sudo docker run -dti --name alarm -p 9912:9912 openfalcon-alarm
```

### Advanced Run

+ Self-defined configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Alarm](http://book.open-falcon.com/zh/install/alarm.html).

+ New falcon-alarm package

    Replace file **falcon-alarm.tar.gz** in the volume */package*.
    
For example, **cfg.json** in /tmp/config and **falcon-alarm.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name alarm -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 9912:9912 openfalcon-alarm
```
