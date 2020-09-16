
# Helper

### Useful terminal commmands:

```bash
#where am I?
pwd

#go to home direcotry:
cd

#one directory up:
cd ..

#go to specific directory:
cd <DIR>

#list files in current directory:
ls
```

<br>

## Useful git commmands:


```bash
#check if something has to be done:
git status

#add changes to stage
git add <file_name or dir_name/>

# or **use with coution**
git add .

# commit changes:
git commit -m "massage"

#push to remote repo:
git push origin master

# or just
git push

```


## Folder structure and docker-compose.yml settings

<br>

### Folder structure:

```
ParentFolder
├── Materials
│   ├── Movies
│   └── Pictures
├── <site_name>.de
│   └── <wordpress>
└── <site_name>_develop
    └── docker-compose.yml
```

### docker-compose.yml settings:
In the wordpress container settings edit the \<name> and \<wordpress> to point to the right folder and set a **UNIQUE** wordpress container name:
```yml
...
wordpress:
    ...
    volumes:
        - ../<site_name>.de/<wordpress>:/var/www/html
    container_name: <NAME>
    ...
```
<br>


## Useful docker-compose commmands:

``` bash
# make sure you're in the <site_name>_develop folder!

# set up and run container stack:
docker-compose up -d

# start container stack:
docker-compose start

# stop container stack:
docker-compose stop

# **delete** container stack:
docker-compose down -v
```