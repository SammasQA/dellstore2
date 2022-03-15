# dellstore2
Примеры простых запросов sql.<br>
В программу обучения входила пратика по базам данным. На примере базы данных PostgreSQL, здесь будут написаны несколько простых sql запросов.
Сам скрипт базы данных тоже будет прикреплен.
<hr>
<dl>
  <dt>SQL запрос для вывода всех категорий</dt>
    <dd>Select * From categories</dd>
  <dt>SQL запрос для вывода только названий всех категорий</dt>
    <dd>Select categoryname From categories</dd>
  <dt>SQL запрос для вывода всех категорий</dt>
    <dd>Select * From categories</dd>
  <dt>Сколько всего категорий?</dt>
    <dd>Select COUNT(categoryname) From categories</dd>
  <dt>SQL запрос для вывода первых 100 строк из таблицы заказов с сортировкой по дате</dt>
    <dd>select * from orders order by orderdate limit 100</dd>
  <dt>SQL запрос для вывода первых 100 строк из таблицы заказов с сортировкой по сумме. От максимальной к минимальной</dt>
    <dd>select * from orders order by totalamount desc limit 100 </dd>
  <dt>SQL запрос для вывода Имени, фамилии, имэйла покупателя с именем «XMFYXD»</dt>
    <dd>select firstname, lastname, email from customers where firstname='XMFYXD'</dd>
  <dt>SQL запрос для вывода списка заказов (id, дата, id покупателя, сумма), совершённых с 2 февраля по 4 февраля</dt>
    <dd>select orderid, orderdate, customerid, totalamount from orders
 where orderdate between '2004-02-02' and '2004-02-04'</dd>
  <dt>Сколько было таких заказов?</dt>
  <dd>select COUNT(orderid) 
from orders where orderdate between '2004-02-02' and '2004-02-04'</dd>
  <dt>SQL запрос для вывода списка актёров и кол-ва фильмов, в которых они снимались</dt>
  <dd>select actor, count(1) from products group by actor</dd>
  <dt>SQL запрос для вывода списка актёров, которые снимались в фильмах не менее 4 раз</dt>
  <dd>select actor, count(1) from products
group by actor having count(1)>=4</dd>
  <dt>SQL запрос для вывода списка позиций заказами с фильмами, в которых снимался CHEVY FOSTER</dt>
  <dd>select * from orderlines inner join products on
orderlines.prod_id=products.prod_id
where actor = 'CHEVY FOSTER'</dd>
  <dt>SQL запрос для вывода покупателей, купивших фильмы с CHEVY FOSTER</dt>
  <dd>select * from customers
where customerid in (
select customerid from orders
where orderid IN (
select orderid from
orderlines inner join products on
orderlines.prod_id=products.prod_id
where actor = 'CHEVY FOSTER'))</dd>      
</dl>

