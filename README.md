# ETL-Pipeline

This my study running ETL Data Process with Apache Airflow running on docker container, for prepparation we need setting environment below;

!. Create folder
2. Download Data Source data to folder

rating.sql ==> https://drive.google.com/file/d/1_wZrrrX7olGhdkgkgnOsp2QAF3FDY64V/view?usp=drive_link



link download 'rating.sql' ==> sudo wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1_wZrrrX7olGhdkgkgnOsp2QAF3FDY64V' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1_wZrrrX7olGhdkgkgnOsp2QAF3FDY64V" -O rating.sql && rm -rf /tmp/cookies.txt

movie.sql==> https://drive.google.com/file/d/1xrSU7uMDSpOAvnopkSuvR4piSyGtx0K3/view?usp=drive_link

link download 'movie.sql' ==> 

3. Import data to mysql server docker container

   mysql -u burhanudiner -p movielens_movie < /home/project/airflow/dags/technical_test_ums/movie.sql

   mysql -u burhanudiner -p movielens_movie < /home/project/airflow/dags/technical_test_ums/rating.sql

   your password : XXXXXXXXXXXX

   CREATE USER 'burhanudiner'@'172.18.X.X';

   GRANT ALL PRIVILEGES ON movielens_movie.* To 'burhanudiner'@'172.18.X.X' IDENTIFIED BY 'XXXXXXXXXXXX';

   atau

   GRANT ALL ON movielens_movie.* TO 'burhanudiner'@'172.18.X.X';

   FLUSH PRIVILEGES;
