1. On docker VM go to this website https://github.com/gustanik/CNA350
2. download into zip file
3. Extact the file to where your comfortable to work with
4. cd into the folder "cd /home/sam/Documents/CNA350-master/maxscale"
5. Run this command docker-compose up -d
6. run this mysql -u maxuser -pmaxpwd -h 127.0.0.1 -P 3306 -e "SELECT *  FROM zipcodes_two.zipcodes_two LIMIT 50;"
7. also this mysql -u maxuser -pmaxpwd -h 127.0.0.1 -P 3306 -e "SELECT *  FROM zipcodes_one.zipcodes_one LIMIT 50;"
8. also check from phpadmin site as well by going into xxx.xxx.xxx.xxx:8080 where xxx.xxx.xxx.xxx is from your vm's ip address you can check it from your host OS for this

output commands as below

sam@loadlugui:~$ cd /home/sam/Documents/CNA350-master/maxscale

sam@loadlugui:~/Documents/CNA350-master/maxscale$ docker-compose up -d
Creating network "maxscale_default" with the default driver
Pulling master (mariadb:latest)...
latest: Pulling from library/mariadb
5bed26d33875: Pull complete
f11b29a9c730: Pull complete
930bda195c84: Pull complete
78bf9a5ad49e: Pull complete
e9e3c043ec68: Pull complete
141e45c6af4b: Pull complete
a26245908a82: Pull complete
40ccaf895c8a: Pull complete
2d665f60c94a: Pull complete
c7bcd9961bee: Pull complete
80f1ddb594ce: Pull complete
0647ec428f9f: Pull complete
9cb6e30e72ca: Pull complete
60890c0035d8: Pull complete
Digest: sha256:d0e2c681c41e91aba6e9c8c0a588eedd48291a70464e83c40da2e3de01998eef
Status: Downloaded newer image for mariadb:latest
Pulling maxscale (mariadb/maxscale:latest)...
latest: Pulling from mariadb/maxscale
5c939e3a4d10: Pull complete
c63719cdbe7a: Pull complete
19a861ea6baf: Pull complete
651c9d2d6c4f: Pull complete
28b221f594a7: Pull complete
fab5b9b792f3: Pull complete
8a61f3f6982e: Pull complete
a1b61bb6cb1d: Pull complete
193868fe6ff8: Pull complete
Digest: sha256:47850957d7ffa555c0a5d93f858537b309f0eafc6be92df3ab801a0513bcba18
Status: Downloaded newer image for mariadb/maxscale:latest
Pulling phpmyadmin (phpmyadmin/phpmyadmin:)...
latest: Pulling from phpmyadmin/phpmyadmin
68ced04f60ab: Pull complete
1d2a5d8fa585: Pull complete
5d59ec4ae241: Pull complete
d42331ef4d44: Pull complete
408b7b7ee112: Pull complete
570cd47896d5: Pull complete
2419413b2a16: Pull complete
8515d21953c8: Pull complete
e307b7ebcc6a: Pull complete
61ed8a3aafe7: Pull complete
b59ff5b10ec9: Pull complete
cb07323f317f: Pull complete
59d7cb052876: Pull complete
dc09551c1560: Pull complete
75b6d22dd505: Pull complete
fb3e41a4fb76: Pull complete
4874cbd79b66: Pull complete
1a7ae8ad19a6: Pull complete
Digest: sha256:59912efb52a5b0342b3defc890a7041ab2a32dc2f5c9a014150006db8c55a793
Status: Downloaded newer image for phpmyadmin/phpmyadmin:latest
Creating maxscale_master2_1 ... done
Creating maxscale_master_1  ... done
Creating maxscale_slave1_1  ... done
Creating maxscale_slave2_1  ... done
Creating maxscale_maxscale_1 ... done
Creating phpmyadmin          ... done

sam@loadlugui:~/Documents/CNA350-master/maxscale$ mysql -u maxuser -pmaxpwd -h 127.0.0.1 -P 3306 -e "SELECT *  FROM zipcodes_two.zipcodes_two LIMIT 50;"
Command 'mysql' not found, but can be installed with:
sudo apt install mysql-client-core-5.7
sudo apt install mariadb-client-core-10.1

sam@loadlugui:~/Documents/CNA350-master/maxscale$ sudo apt install mariadb-client-core-10.1
[sudo] password for sam:
Sorry, try again.
[sudo] password for sam:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  libreadline5 mariadb-common
The following NEW packages will be installed:
  libreadline5 mariadb-client-core-10.1 mariadb-common
0 upgraded, 3 newly installed, 0 to remove and 498 not upgraded.
Need to get 4,888 kB of archives.
After this operation, 24.5 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu bionic/main amd64 libreadline5 amd64 5.2+dfsg-3build1 [99.5 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 mariadb-common all 1:10.1.44-0ubuntu0.18.04.1 [16.1 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 mariadb-client-core-10.1 amd64 1:10.1.44-0ubuntu0.18.04.1 [4,772 kB]
Fetched 4,888 kB in 2s (2,564 kB/s)
Selecting previously unselected package libreadline5:amd64.
(Reading database ... 103394 files and directories currently installed.)
Preparing to unpack .../libreadline5_5.2+dfsg-3build1_amd64.deb ...
Unpacking libreadline5:amd64 (5.2+dfsg-3build1) ...
Selecting previously unselected package mariadb-common.
Preparing to unpack .../mariadb-common_1%3a10.1.44-0ubuntu0.18.04.1_all.deb ...
Unpacking mariadb-common (1:10.1.44-0ubuntu0.18.04.1) ...
Selecting previously unselected package mariadb-client-core-10.1.
Preparing to unpack .../mariadb-client-core-10.1_1%3a10.1.44-0ubuntu0.18.04.1_amd64.deb ...
Unpacking mariadb-client-core-10.1 (1:10.1.44-0ubuntu0.18.04.1) ...
Setting up mariadb-common (1:10.1.44-0ubuntu0.18.04.1) ...
update-alternatives: using /etc/mysql/mariadb.cnf to provide /etc/mysql/my.cnf (my.cnf) in auto mode
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Processing triggers for man-db (2.8.3-2) ...
Setting up libreadline5:amd64 (5.2+dfsg-3build1) ...
Setting up mariadb-client-core-10.1 (1:10.1.44-0ubuntu0.18.04.1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...

sam@loadlugui:~/Documents/CNA350-master/maxscale$ mysql -u maxuser -pmaxpwd -h 127.0.0.1 -P 3306 -e "SELECT *  FROM zipcodes_two.zipcodes_two LIMIT 50;"
+---------+-------------+---------------+-------+--------------+-----------+------------+------------------------+---------------+-----------------+---------------------+------------+
| Zipcode | ZipCodeType | City          | State | LocationType | Coord_Lat | Coord_Long | Location               | Decommisioned | TaxReturnsFiled | EstimatedPopulation | TotalWages |
+---------+-------------+---------------+-------+--------------+-----------+------------+------------------------+---------------+-----------------+---------------------+------------+
|   42040 | STANDARD    | FARMINGTON    | KY    | PRIMARY      | 36.67     | -88.53     | NA-US-KY-FARMINGTON    | FALSE         | 465             | 896                 | 11562973   |
|   41524 | STANDARD    | FEDSCREEK     | KY    | PRIMARY      | 37.4      | -82.24     | NA-US-KY-FEDSCREEK     | FALSE         |                 |                     |            |
|   42533 | STANDARD    | FERGUSON      | KY    | PRIMARY      | 37.06     | -84.59     | NA-US-KY-FERGUSON      | FALSE         | 429             | 761                 | 9555412    |
|   40022 | STANDARD    | FINCHVILLE    | KY    | PRIMARY      | 38.15     | -85.31     | NA-US-KY-FINCHVILLE    | FALSE         | 437             | 839                 | 19909942   |
|   40023 | STANDARD    | FISHERVILLE   | KY    | PRIMARY      | 38.16     | -85.42     | NA-US-KY-FISHERVILLE   | FALSE         | 1884            | 3733                | 113020684  |
|   41743 | PO BOX      | FISTY         | KY    | PRIMARY      | 37.33     | -83.1      | NA-US-KY-FISTY         | FALSE         |                 |                     |            |
|   41219 | STANDARD    | FLATGAP       | KY    | PRIMARY      | 37.93     | -82.88     | NA-US-KY-FLATGAP       | FALSE         | 708             | 1397                | 20395667   |
|   40935 | STANDARD    | FLAT LICK     | KY    | PRIMARY      | 36.82     | -83.76     | NA-US-KY-FLAT LICK     | FALSE         | 752             | 1477                | 14267237   |
|   40997 | STANDARD    | WALKER        | KY    | PRIMARY      | 36.88     | -83.71     | NA-US-KY-WALKER        | FALSE         |                 |                     |            |
|   41139 | STANDARD    | FLATWOODS     | KY    | PRIMARY      | 38.51     | -82.72     | NA-US-KY-FLATWOODS     | FALSE         | 3692            | 6748                | 121902277  |
|   41526 | PO BOX      | FORDS BRANCH  | KY    | PRIMARY      | 37.32     | -82.57     | NA-US-KY-FORDS BRANCH  | FALSE         |                 |                     |            |
|   42343 | STANDARD    | FORDSVILLE    | KY    | PRIMARY      | 37.63     | -86.71     | NA-US-KY-FORDSVILLE    | FALSE         | 735             | 1360                | 18216579   |
|   42361 | STANDARD    | OLATON        | KY    | PRIMARY      | 37.53     | -86.7      | NA-US-KY-OLATON        | FALSE         |                 |                     |            |
|   41527 | STANDARD    | FOREST HILLS  | KY    | PRIMARY      | 37.63     | -82.29     | NA-US-KY-FOREST HILLS  | FALSE         |                 |                     |            |
|   42223 | STANDARD    | FORT CAMPBELL | KY    | PRIMARY      | 36.65     | -87.54     | NA-US-KY-FORT CAMPBELL | FALSE         | 6776            | 13815               | 129784441  |
|   40121 | STANDARD    | FORT KNOX     | KY    | PRIMARY      | 37.89     | -85.96     | NA-US-KY-FORT KNOX     | FALSE         | 2833            | 6397                | 101583167  |
|   40122 | STANDARD    | FORT KNOX     | KY    | PRIMARY      | 37.89     | -85.96     | NA-US-KY-FORT KNOX     | FALSE         |                 |                     |            |
|   42133 | STANDARD    | FOUNTAIN RUN  | KY    | PRIMARY      | 36.72     | -85.96     | NA-US-KY-FOUNTAIN RUN  | FALSE         | 566             | 1042                | 12711806   |
|   40939 | STANDARD    | FOURMILE      | KY    | PRIMARY      | 36.79     | -83.74     | NA-US-KY-FOURMILE      | FALSE         |                 |                     |            |
|   40940 | STANDARD    | FRAKES        | KY    | PRIMARY      | 36.64     | -83.92     | NA-US-KY-FRAKES        | FALSE         |                 |                     |            |
|   40601 | STANDARD    | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         | 22938           | 39539               | 721803780  |
|   40602 | PO BOX      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         | 562             | 872                 | 15398719   |
|   40603 | PO BOX      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   40604 | PO BOX      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   40618 | UNIQUE      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   40619 | UNIQUE      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   40620 | UNIQUE      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   40621 | UNIQUE      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         | 308             | 309                 | 429045     |
|   40622 | UNIQUE      | FRANKFORT     | KY    | PRIMARY      | 38.19     | -84.86     | NA-US-KY-FRANKFORT     | FALSE         |                 |                     |            |
|   42134 | STANDARD    | FRANKLIN      | KY    | PRIMARY      | 36.72     | -86.57     | NA-US-KY-FRANKLIN      | FALSE         | 7045            | 12759               | 204138728  |
|   42135 | PO BOX      | FRANKLIN      | KY    | PRIMARY      | 36.72     | -86.57     | NA-US-KY-FRANKLIN      | FALSE         | 412             | 700                 | 11442122   |
|   42411 | STANDARD    | FREDONIA      | KY    | PRIMARY      | 37.2      | -88.05     | NA-US-KY-FREDONIA      | FALSE         | 709             | 1340                | 19718071   |
|   41528 | STANDARD    | FREEBURN      | KY    | PRIMARY      | 37.54     | -82.14     | NA-US-KY-FREEBURN      | FALSE         |                 |                     |            |
|   40322 | STANDARD    | FRENCHBURG    | KY    | PRIMARY      | 37.95     | -83.62     | NA-US-KY-FRENCHBURG    | FALSE         | 1215            | 2297                | 29301156   |
|   42041 | STANDARD    | FULTON        | KY    | PRIMARY      | 36.51     | -88.88     | NA-US-KY-FULTON        | FALSE         | 1884            | 3357                | 41829720   |
|   42140 | STANDARD    | GAMALIEL      | KY    | PRIMARY      | 36.63     | -85.79     | NA-US-KY-GAMALIEL      | FALSE         | 505             | 948                 | 10871559   |
|   40140 | STANDARD    | GARFIELD      | KY    | PRIMARY      | 37.78     | -86.35     | NA-US-KY-GARFIELD      | FALSE         | 303             | 590                 | 8251697    |
|   41817 | STANDARD    | GARNER        | KY    | PRIMARY      | 37.35     | -82.92     | NA-US-KY-GARNER        | FALSE         |                 |                     |            |
|   40941 | PO BOX      | GARRARD       | KY    | PRIMARY      | 37.12     | -83.74     | NA-US-KY-GARRARD       | FALSE         | 269             | 523                 | 4354249    |
|   41630 | STANDARD    | GARRETT       | KY    | PRIMARY      | 37.48     | -82.83     | NA-US-KY-GARRETT       | FALSE         | 452             | 861                 | 12457690   |
|   41632 | STANDARD    | GUNLOCK       | KY    | PRIMARY      | 37.54     | -82.92     | NA-US-KY-GUNLOCK       | FALSE         |                 |                     |            |
|   41141 | STANDARD    | GARRISON      | KY    | PRIMARY      | 38.55     | -83.19     | NA-US-KY-GARRISON      | FALSE         | 935             | 1908                | 24423389   |
|   41745 | STANDARD    | GAYS CREEK    | KY    | PRIMARY      | 37.33     | -83.4      | NA-US-KY-GAYS CREEK    | FALSE         |                 |                     |            |
|   40324 | STANDARD    | GEORGETOWN    | KY    | PRIMARY      | 38.2      | -84.55     | NA-US-KY-GEORGETOWN    | FALSE         | 17361           | 32541               | 775385492  |
|   42044 | STANDARD    | GILBERTSVILLE | KY    | PRIMARY      | 36.96     | -88.27     | NA-US-KY-GILBERTSVILLE | FALSE         | 1562            | 2844                | 50607538   |
|   40943 | STANDARD    | GIRDLER       | KY    | PRIMARY      | 36.93     | -83.84     | NA-US-KY-GIRDLER       | FALSE         | 364             | 748                 | 9130115    |
|   42131 | STANDARD    | ETOILE        | KY    | PRIMARY      | 36.81     | -85.91     | NA-US-KY-ETOILE        | FALSE         |                 |                     |            |
|   42141 | STANDARD    | GLASGOW       | KY    | PRIMARY      | 36.99     | -85.92     | NA-US-KY-GLASGOW       | FALSE         | 12376           | 22835               | 367606457  |
|   42142 | PO BOX      | GLASGOW       | KY    | PRIMARY      | 36.99     | -85.92     | NA-US-KY-GLASGOW       | FALSE         | 493             | 812                 | 12735248   |
|   42156 | STANDARD    | LUCAS         | KY    | PRIMARY      | 36.88     | -86.03     | NA-US-KY-LUCAS         | FALSE         |                 |                     |            |
+---------+-------------+---------------+-------+--------------+-----------+------------+------------------------+---------------+-----------------+---------------------+------------+

sam@loadlugui:~/Documents/CNA350-master/maxscale$ mysql -u maxuser -pmaxpwd -h 127.0.0.1 -P 3306 -e "SELECT *  FROM zipcodes_one.zipcodes_one LIMIT 50;"
+---------+-------------+--------------------+-------+--------------+-----------+------------+-----------------------------+---------------+-----------------+---------------------+------------+
| Zipcode | ZipCodeType | City               | State | LocationType | Coord_Lat | Coord_Long | Location                    | Decommisioned | TaxReturnsFiled | EstimatedPopulation | TotalWages |
+---------+-------------+--------------------+-------+--------------+-----------+------------+-----------------------------+---------------+-----------------+---------------------+------------+
|     705 | STANDARD    | AIBONITO           | PR    | PRIMARY      | 18.14     | -66.26     | NA-US-PR-AIBONITO           | FALSE         |                 |                     |            |
|     610 | STANDARD    | ANASCO             | PR    | PRIMARY      | 18.28     | -67.14     | NA-US-PR-ANASCO             | FALSE         |                 |                     |            |
|     611 | PO BOX      | ANGELES            | PR    | PRIMARY      | 18.28     | -66.79     | NA-US-PR-ANGELES            | FALSE         |                 |                     |            |
|     612 | STANDARD    | ARECIBO            | PR    | PRIMARY      | 18.45     | -66.73     | NA-US-PR-ARECIBO            | FALSE         |                 |                     |            |
|     601 | STANDARD    | ADJUNTAS           | PR    | PRIMARY      | 18.16     | -66.72     | NA-US-PR-ADJUNTAS           | FALSE         |                 |                     |            |
|     631 | PO BOX      | CASTANER           | PR    | PRIMARY      | 18.19     | -66.82     | NA-US-PR-CASTANER           | FALSE         |                 |                     |            |
|     602 | STANDARD    | AGUADA             | PR    | PRIMARY      | 18.38     | -67.18     | NA-US-PR-AGUADA             | FALSE         |                 |                     |            |
|     603 | STANDARD    | AGUADILLA          | PR    | PRIMARY      | 18.43     | -67.15     | NA-US-PR-AGUADILLA          | FALSE         |                 |                     |            |
|     604 | PO BOX      | AGUADILLA          | PR    | PRIMARY      | 18.43     | -67.15     | NA-US-PR-AGUADILLA          | FALSE         |                 |                     |            |
|     605 | PO BOX      | AGUADILLA          | PR    | PRIMARY      | 18.43     | -67.15     | NA-US-PR-AGUADILLA          | FALSE         |                 |                     |            |
|     703 | STANDARD    | AGUAS BUENAS       | PR    | PRIMARY      | 18.25     | -66.1      | NA-US-PR-AGUAS BUENAS       | FALSE         |                 |                     |            |
|     704 | STANDARD    | AGUIRRE            | PR    | PRIMARY      | 17.96     | -66.22     | NA-US-PR-AGUIRRE            | FALSE         |                 |                     |            |
|    7675 | STANDARD    | WESTWOOD           | NJ    | PRIMARY      | 40.98     | -74.03     | NA-US-NJ-WESTWOOD           | FALSE         | 13245           | 24083               | 1089095041 |
|    7677 | STANDARD    | WOODCLIFF LAKE     | NJ    | PRIMARY      | 41.02     | -74.05     | NA-US-NJ-WOODCLIFF LAKE     | FALSE         | 2945            | 5471                | 325436960  |
|    7885 | STANDARD    | WHARTON            | NJ    | PRIMARY      | 40.89     | -74.58     | NA-US-NJ-WHARTON            | FALSE         | 5273            | 8999                | 240827990  |
|    7981 | STANDARD    | WHIPPANY           | NJ    | PRIMARY      | 40.82     | -74.41     | NA-US-NJ-WHIPPANY           | FALSE         | 4585            | 8057                | 292096795  |
|    7999 | STANDARD    | WHIPPANY           | NJ    | PRIMARY      | 40.82     | -74.41     | NA-US-NJ-WHIPPANY           | FALSE         |                 |                     |            |
|    8888 | PO BOX      | WHITEHOUSE         | NJ    | PRIMARY      | 40.62     | -74.76     | NA-US-NJ-WHITEHOUSE         | FALSE         |                 |                     |            |
|    8889 | STANDARD    | WHITEHOUSE STATION | NJ    | PRIMARY      | 40.6      | -74.76     | NA-US-NJ-WHITEHOUSE STATION | FALSE         | 4691            | 8570                | 401312434  |
|    7095 | STANDARD    | WOODBRIDGE         | NJ    | PRIMARY      | 40.55     | -74.28     | NA-US-NJ-WOODBRIDGE         | FALSE         | 10018           | 17272               | 528315021  |
|    7481 | STANDARD    | WYCKOFF            | NJ    | PRIMARY      | 40.99     | -74.16     | NA-US-NJ-WYCKOFF            | FALSE         | 8079            | 15208               | 896273759  |
|   10451 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 19434           | 31477               | 471446942  |
|   10452 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 33517           | 56277               | 723508523  |
|   10453 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 34152           | 57691               | 699611756  |
|   10454 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 13139           | 22387               | 273119576  |
|   10455 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 14914           | 25139               | 325274189  |
|   10456 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 34793           | 58750               | 732907466  |
|   10457 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 29023           | 48779               | 614273091  |
|   10458 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 29920           | 50085               | 693447254  |
|   10459 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 17977           | 30434               | 414021653  |
|   10460 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 23466           | 39507               | 531807385  |
|   10461 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 21862           | 35421               | 839765651  |
|   10462 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 35620           | 57854               | 1197519842 |
|   10463 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 31592           | 50313               | 1284853119 |
|   10464 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 2131            | 3381                | 108256016  |
|   10465 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 18686           | 30798               | 817052868  |
|   10466 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 29153           | 47658               | 924776075  |
|   10467 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 39540           | 64907               | 1114305720 |
|   10468 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 34706           | 55824               | 840612915  |
|   10469 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 28964           | 47625               | 1017556583 |
|   10470 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 7000            | 10880               | 260963512  |
|   10471 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 9876            | 15606               | 623827705  |
|   10472 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 26025           | 43761               | 630416228  |
|   10473 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 26122           | 42812               | 817850845  |
|   10474 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 4369            | 7377                | 97578251   |
|   10475 | STANDARD    | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         | 21124           | 31659               | 740068715  |
|   10499 | UNIQUE      | BRONX              | NY    | PRIMARY      | 40.84     | -73.87     | NA-US-NY-BRONX              | FALSE         |                 |                     |            |
|   10001 | STANDARD    | NEW YORK           | NY    | PRIMARY      | 40.71     | -73.99     | NA-US-NY-NEW YORK           | FALSE         | 12534           | 16553               | 1031960117 |
|   10002 | STANDARD    | NEW YORK           | NY    | PRIMARY      | 40.71     | -73.99     | NA-US-NY-NEW YORK           | FALSE         | 45236           | 70604               | 1394042364 |
|   10003 | STANDARD    | NEW YORK           | NY    | PRIMARY      | 40.71     | -73.99     | NA-US-NY-NEW YORK           | FALSE         | 28817           | 36569               |            |
+---------+-------------+--------------------+-------+--------------+-----------+------------+-----------------------------+---------------+-----------------+---------------------+------------+
