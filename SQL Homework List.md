<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

# SQL Homework List

## SQL Homework 1

<details close>
<summary><i>Homework1 Content</i></summary></br>

1- film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

`js SELECT title,description FROM film;`

---

2- film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

`SELECT * FROM film WHERE length>60 AND length<75; `

---

3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

`SELECT * FROM film WHERE rental_rate=0.99 AND (replacement_cost=12.99 OR replacement_cost=28.99);`

---

4-customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

#### Cevap 'Smith'

`SELECT * FROM customer WHERE first_name='Mary';`

---

5-film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

`SELECT * FROM film WHERE NOT length>50 AND NOT (rental_rate=2.99 OR rental_rate=4.99);`

</details>
&nbsp;
&nbsp;

---

## SQL Homework 2

<details close>
<summary> <i>Homework2 Content</i> </summary> </br>

1- film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

`SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;`

---

2- .actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

`SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed');`

---

3- film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

`SELECT * FROM film WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99);`

</details>
&nbsp;
&nbsp;

---

## SQL Homework 3

<details close>

  <summary><i>Homework3 Content</i></summary> </br>

1- country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

`SELECT * FROM country WHERE country LIKE 'A%a';`

---

2- country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

`SELECT * FROM country WHERE country LIKE '_____n';`

---

3- film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

`SELECT title FROM film WHERE title ILIKE '%t%t%t%t%';`

4- film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

`SELECT * FROM film WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 4

<details close>
  <summary><i>Homework4 Content</i></summary> </br>

1- film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

`SELECT DISTINCT replacement_cost FROM film;  `

---

2- film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

Cevap 21

`SELECT COUNT(DISTINCT replacement_cost) FROM film;`

---

3- film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

Cevap 9

`SELECT COUNT(*) FROM film WHERE title LIKE 'T%' AND rating = 'G'; `

---

4- country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

Cevap 13

`SELECT COUNT(DISTINCT country) FROM country WHERE country LIKE '_____';`

---

5- city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

`SELECT COUNT(city) FROM city WHERE city ILIKE ('%R');`

</details>
&nbsp;
&nbsp;

---

## SQL Homework 5

<details close>
  <summary><i>Homework5 Content</i></summary> </br>

1- film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

---

`SELECT title FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5; `

2- film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

---

`SELECT title FROM film WHERE title LIKE '%n' ORDER BY length ASC OFFSET 1 LIMIT 1;`

3- customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

`SELECT * FROM customer  WHERE store_id = 1 ORDER BY last_name DESC LIMIT 4;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 6

<details close>
  <summary><i>Homework6 Content</i></summary> </br>
    
  1- film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

`SELECT ROUND(AVG(rental_rate),2) FROM film; `

---

2- film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

`SELECT COUNT(*) FROM film WHERE title LIKE 'C%';`

---

3- film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

`SELECT COUNT(*) FROM film WHERE title LIKE 'C%';`

---

4- film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

`SELECT COUNT(DISTINCT replacement_cost) FROM film WHERE length > 150 ;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 7

<details close>
  <summary><i>Homework7 Content</i></summary> </br>
    
1- film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

---

`SELECT rating, COUNT(*) FROM film
GROUP BY rating;`

2- film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

---

`SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost HAVING COUNT(*)> 50;`

3-customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

---

`SELECT store_id , COUNT(customer_id) FROM customer
GROUP BY store_id;`

4- city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

`SELECT country_id,COUNT(country_id) FROM city GROUP BY country_id  ORDER BY COUNT(country_id) DESC LIMIT 1;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 8

<details close>
  <summary><i>Homework8 Content</i></summary> </br>
    
  PASSED

</details>

&nbsp;
&nbsp;

---

## SQL Homework 9

<details close>
  <summary><i>Homework9 Content</i></summary> </br>
    
1- city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

`SELECT city.city,country.country FROM country INNER JOIN city ON city.country_id = country.country_id;`

---

2- customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

`SELECT payment.payment_id,CONCAT(customer.first_name, ' ' ,customer.last_name) as full_name FROM customer INNER JOIN payment ON customer.customer_id = payment.customer_id;`

---

3- customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

`SELECT rental.rental_id,CONCAT(customer.first_name, ' ' ,customer.last_name) as full_name FROM customer INNER JOIN rental ON customer.customer_id = rental.customer_id;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 10

<details close>
  <summary><i>Homework10 Content</i></summary> </br>
    
1- city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

` SELECT city.city,country.country FROM city LEFT JOIN country ON city.country_id = country.country_id;`

---

2- customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.

`SELECT payment.payment_id,customer.first_name,customer.last_name FROM customer RIGHT JOIN payment ON customer.customer_id = payment.customer_id;`

---

3- customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

` SELECT customer.first_name, customer.last_name, rental.rental_id FROM customer FULL JOIN rental ON rental.customer_id = customer.customer_id;`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 11

<details close>
  <summary><i>Homework11 Content</i></summary> </br>

1- actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.

`(SELECT first_name FROM actor) UNION (SELECT first_name FROM customer);`

---

2- actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.

`(SELECT first_name FROM actor) INTERSECT (SELECT first_name FROM customer);`

---

3- actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

`(SELECT first_name FROM actor) EXCEPT (SELECT first_name FROM customer);`

---

4- İlk 3 sorguyu tekrar eden veriler için de yapalım.

`(SELECT first_name FROM actor) UNION ALL (SELECT first_name FROM customer);`

`(SELECT first_name FROM actor) INTERSECT ALL (SELECT first_name FROM customer);`

`(SELECT first_name FROM actor) EXCEPT ALL (SELECT first_name FROM customer);`

</details>

&nbsp;
&nbsp;

---

## SQL Homework 12

<details close>
  <summary><i>Homework12 Content</i></summary> </br>

1- film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?

`SELECT COUNT(film_id) FROM film WHERE length > (SELECT AVG(length) FROM film);`

---

2- film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

`SELECT COUNT(film_id) FROM film WHERE rental_rate = (SELECT MAX(rental_rate) FROM film );`

---

3- film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.

```
SELECT title,rental_rate,replacement_cost FROM film WHERE rental_rate =
(
	SELECT MIN(rental_rate) FROM film
)
AND
replacement_cost =
(
	SELECT MIN(replacement_cost) FROM film
)
ORDER BY title DESC;

```

---

4- payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

```
SELECT payment.customer_id, customer.first_name, customer.last_name,  COUNT(payment.customer_id)
FROM payment
INNER JOIN customer ON customer.customer_id = payment.customer_id
GROUP BY customer.first_name, customer.last_name, payment.customer_id
ORDER BY COUNT(payment.customer_id) DESC;

```

</details>
