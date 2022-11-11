# WDD MySQL Server - MySQL Server Container

This is a MYSQL Server container to be used in conjunction with the WDD PHP/Apache2 container to provide a full LAMP stack.

To use this container, you need Docker Desktop installed on your system.

Download Docker Desktop here: [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)

## Instructions

**Before you begin:** _Make sure you shut down XAMPP, MAMP, or WAMP.  Halt any Vagrant machines you are using.  If you are running Apache or MySQL as Windows Services, turn them off.  If any of these are running, they will interfere with the port requirements for the php/apache and mariadb containers, and the containers will not start.  Alternatively, edit the `.env` file and change the `LOCAL_HTTP_PORT` or `LOCAL_MYSQL_PORT` values in the container's respective `.env` files._

* Download a zip archive of this repository.  I recommend putting it somewhere that is not backed up by OneDrive or Dropbox... there will be a lot of changing files, and syncing with a backup service could slow your system.


* The default settings in `docker-compose.yml` should work just fine, but you can edit this file if you need to.

* You have a `persist` folder inside this folder, where all the database files from the container will be saved.  Even if the container is destroyed, your data will be preserved

* When you are ready, run the following command, inside this folder. 

```bash
    # --build required on first run only
    docker-compose up -d --build
```

* After the image downloads and the container builds and runs (could take 2 minutes for first run), check the Docker Desktop dashboard.  You should see something like this:

![](https://73d7ee5cf3d33ba6c54d-02c37edeb863bbff92ffd1f4f4d94138.ssl.cf2.rackcdn.com/screenshot.jpg)

* To use this container with PHP and Apache, you also need to download the WDD PHP/Apache2 Container and follow the instructions in its README files.

* After the first run, you can manage the MYSQL Server container through the Docker Desktop dashboard, or from a bash shell using the following commands:

```bash

    # To gracefully shut down your container
    docker-compose down

    # To start your container
    docker-compose up -d

    # Note: the -d flag detaches the container process so you
    # don't have to keep the terminal open while it's running.

```

## MySQL Client

To use the MySQL Server container from the host system (Windows or Mac), you need a MySQL Monitor client; a MariaDB client will not work properly in this case.

If you install MySQLWorkbench (Highly recommended!), a MySQL Monitor client is installed along with it.  All you need to do is add the MySQLMonitor folder path to your Environment PATH:

```
C:\Windows\Program Files\MySQL\MySQLMonitor
```

In Mac, edit `/etc/paths` and add the path to the MySQLWorkbench MacOS folder.

```
/Applications/MySQLWorkbench.app/contents/MacOS
```

  
  
