# Senac-Resilia-Projeto-04
4º projeto em grupo do curso de programação do Senac-Resilia, um banco de dados sobre Game of Thrones.
https://www.canva.com/design/DAFafjRJ-9I/FsyiahKAzwa2tALKjIjXRA/edit?utm_content=DAFafjRJ-9I&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

create table characters_v4(
Character varchar(34) primary key,
Actor/ess varchar(27),
Episodes_appeared int(2),
First_appearance int(4),
Last_appearance int(4));

create table got_episodes_v4(
Season int(1),
Episode int(2),
Title varchar(37) primary key,
Release_date varchar(9),
Rating decimal(2,1),
Votes int(6),
Summary varchar(238),
Writer_1 varchar(18),
Writer_2 varchar(13),
Star_1 varchar(21),
Star_2 varchar(21),
Star_3 varchar(21),
Users_reviews int(4),
Critics_reviews int(2),
US_viewers decimal(4,2),
Duration int(2),
Director varchar(18),
Budget_estimate int(1));

create table houses_v1(
House_name varchar(33) primary key,
Region varchar(41));


# Quais personagens sobreviveram da primeira à ultima temporada?
select * from characters_v4 where (Last_appearance - First_appearance) > 7;
+----------------------------+------------------------+-------------------+------------------+-----------------+
| Character                  | Actor/ess              | Episodes_appeared | First_appearance | Last_appearance |
+----------------------------+------------------------+-------------------+------------------+-----------------+
| Tyrion Lannister           | Peter Dinklage         |                67 |             2011 |            2019 |
| Cersei Lannister           | Lena Headey            |                62 |             2011 |            2019 |
| Daenerys Targaryen         | Emilia Clarke          |                62 |             2011 |            2019 |
| Jon Snow                   | Kit Harington          |                62 |             2011 |            2019 |
| Sansa Stark                | Sophie Turner          |                59 |             2011 |            2019 |
| Arya Stark                 | Maisie Williams        |                59 |             2011 |            2019 |
| Jaime Lannister            | Nikolaj Coster-Waldau  |                55 |             2011 |            2019 |
| Jorah Mormont              | Iain Glen              |                52 |             2011 |            2019 |
| Samwell Tarly              | John Bradley           |                48 |             2011 |            2019 |
| Theon Greyjoy              | Alfie Allen            |                47 |             2011 |            2019 |
| Lord Varys                 | Conleth Hill           |                46 |             2011 |            2019 |
| Bran Stark                 | Isaac Hempstead Wright |                40 |             2011 |            2019 |
| Sandor 'The Hound' Clegane | Rory McCann            |                38 |             2011 |            2019 |
| Bronn                      | Jerome Flynn           |                37 |             2011 |            2019 |
| Gendry                     | Joe Dempsie            |                24 |             2011 |            2019 |
| Wun Wun                    | Ian Whyte              |                16 |             2011 |            2019 |
| Robin Arryn                | Lino Facioli           |                 9 |             2011 |            2019 |
+----------------------------+------------------------+-------------------+------------------+-----------------+
17 rows in set (0.001 sec)

# Os 10 episódios de menor audiência:
select Season, Episode, Title, US_Viewers from got_episodes_v4 order by US_Viewers limit 10;
+--------+---------+---------------------------------------+------------+
| Season | Episode | Title                                 | US_Viewers |
+--------+---------+---------------------------------------+------------+
|      1 |       2 | The Kingsroad                         |       2.20 |
|      1 |       1 | Winter Is Coming                      |       2.22 |
|      1 |       7 | You Win or You Die                    |       2.40 |
|      1 |       6 | A Golden Crown                        |       2.44 |
|      1 |       3 | Lord Snow                             |       2.44 |
|      1 |       4 | Cripples, Bastards, and Broken Things |       2.45 |
|      1 |       5 | The Wolf and the Lion                 |       2.58 |
|      1 |       9 | Baelor                                |       2.66 |
|      1 |       8 | The Pointy End                        |       2.72 |
|      1 |      10 | Fire and Blood                        |       3.04 |
+--------+---------+---------------------------------------+------------+
10 rows in set (0.001 sec)

# Os 20 personagens com mais aparições:
select * from characters_v4 order by Episodes_appeared DESC limit 20;
+------------------------------+------------------------+-------------------+------------------+-----------------+
| Character                    | Actor/ess              | Episodes_appeared | First_appearance | Last_appearance |
+------------------------------+------------------------+-------------------+------------------+-----------------+
| Tyrion Lannister             | Peter Dinklage         |                67 |             2011 |            2019 |
| Cersei Lannister             | Lena Headey            |                62 |             2011 |            2019 |
| Daenerys Targaryen           | Emilia Clarke          |                62 |             2011 |            2019 |
| Jon Snow                     | Kit Harington          |                62 |             2011 |            2019 |
| Arya Stark                   | Maisie Williams        |                59 |             2011 |            2019 |
| Sansa Stark                  | Sophie Turner          |                59 |             2011 |            2019 |
| Jaime Lannister              | Nikolaj Coster-Waldau  |                55 |             2011 |            2019 |
| Jorah Mormont                | Iain Glen              |                52 |             2011 |            2019 |
| Samwell Tarly                | John Bradley           |                48 |             2011 |            2019 |
| Theon Greyjoy                | Alfie Allen            |                47 |             2011 |            2019 |
| Lord Varys                   | Conleth Hill           |                46 |             2011 |            2019 |
| Davos Seaworth               | Liam Cunningham        |                42 |             2012 |            2019 |
| Brienne of Tarth             | Gwendoline Christie    |                42 |             2012 |            2019 |
| Petyr 'Littlefinger' Baelish | Aidan Gillen           |                41 |             2011 |            2017 |
| Bran Stark                   | Isaac Hempstead Wright |                40 |             2011 |            2019 |
| Missandei                    | Nathalie Emmanuel      |                38 |             2013 |            2019 |
| Sandor 'The Hound' Clegane   | Rory McCann            |                38 |             2011 |            2019 |
| Bronn                        | Jerome Flynn           |                37 |             2011 |            2019 |
| Podrick Payne                | Daniel Portman         |                35 |             2012 |            2019 |
| Eddison Tollett              | Ben Crompton           |                34 |             2012 |            2019 |
+------------------------------+------------------------+-------------------+------------------+-----------------+
20 rows in set (0.002 sec)

# Quantas casas nobres ficam no Norte?
+-------------------+
| count(House_name) |
+-------------------+
|                48 |
+-------------------+
1 row in set (0.001 sec)

# Quais casas nobres de que regiões começam com a letra U?
select House_name, Region from houses_v1 where House_name like 'u%';
+---------------------------+---------------+
| House_name                | Region        |
+---------------------------+---------------+
| Uffering                  | Reach         |
| Uller of the Hellholt     | Dorne         |
| Umber of the Last Hearth  | North         |
| Upcliff of the Witch Isle | Vale of Arryn |
+---------------------------+---------------+
4 rows in set (0.002 sec)
