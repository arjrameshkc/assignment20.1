# assignment20.1

	
mysql -u root

create database db1;

use db1;

create table company
(
id int,
name varchar(20),
location varchar(20)
);

insert into company values(1, 'acadgild','Bangalore');

insert into company values(2, 'eduvista','Walnut');

insert into company values(3, 'eduvista','Bangalore');

grant all on *.* to 'root'@'localhost' with grant option;


sqoop export --connect jdbc:mysql://localhost/db1 --username 'root' -P --table 'company' --export-dir '/sqoopout' --input-fields-terminated-by ',' --update-key id 
