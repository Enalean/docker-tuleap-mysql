A mysql55 container tailored for Tuleap usage

Usage
=====

Create a data volume to make your write persistent
   $> docker run --name=dbdata -v /var/lib/mysql centos true

Note: you should never delete this container otherwise your data will be gone.

Initialize a new DB:

    $> docker run --rm=true -e MYSQL_ROOT_PASSWORD=welcome0 --volumes-from=dbdata enalean/tuleap-db

Run the DB:

   $> docker run -d --volumes-from=dbdata enalean/tuleap-db
