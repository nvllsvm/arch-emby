**Application**

[emby-unlocked](https://github.com/nvllsvm/emby-unlocked)

**Description**

Emby Server is a home media server built on top of other popular open source technologies such as Service Stack, jQuery, jQuery mobile, and Mono.
This is the Emby Server patched to unlock Emby Premiere features.

**Build notes**

Latest [emby-server-unlocked](https://aur.archlinux.org/packages/emby-server-unlocked/) from the Arch Linux AUR.

**Usage**
```
docker run -d \
    -p 8096:8096 \
    --name=<container name> \
    -v <path for media files>:/media \
    -v <path for config files>:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e UMASK=<umask for created files> \
    -e PUID=<uid for user> \
    -e PGID=<gid for user> \
    nvllsvm/emby-unlocked
```

Please replace all user variables in the above command defined by <> with the correct values.

**Access application**

`<host ip>:8096`

**Example**
```
docker run -d \
    -p 8096:8096 \
    --name=emby-server \
    -v /media/movies:/media \
    -v /apps/docker/emby/config:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    nvllsvm/emby-unlocked
```

**Notes**

User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:-

```
id <username>
```
