# -----------------------------Update-------------------------------------------------------------------------------------------
```sql
UPDATE customers
Set first_name = 'Batu' , last_name = 'keskin'
where customer_id = 1
```
![update](https://user-images.githubusercontent.com/77542685/204286831-cb54072d-dd68-4c73-9b13-9bc28e4f90d4.png)

# --------------------------------Insert Into---------------------------------

```sql
INSERT INTO Customer (name,first_name,last_name,email,phone_number)
VALUES ('Eren','Erdoğan',Ernerdgn@gmail.com,05869485847)
Select * from customers
```
![Screenshot 2022-11-28 162445](https://user-images.githubusercontent.com/77542685/204288756-055cebba-9f0f-494e-82c9-c28dad6bcf94.png)

# ---------------------------------Between----------------------------------
```sql
--Product tablosunda ki fiyat aralığı  0 ve 10 aralığında bulunan ürünlere indirim uygulanıp sıralaması yapıldı.
UPDATE products SET unit_price =unit_price-3
WHERE unit_price BETWEEN 0 AND 10;
SELECT name , unit_price FROM products WHERE unit_price BETWEEN 0 AND 10;
```
![luppo](https://user-images.githubusercontent.com/77542685/204289657-eba71d5b-79e9-499a-a42e-d68ea3a92b2c.png)
# ----------------------------------Delete----------------------------------
```sql 
Delete from  addresses where address_id = 1  
select * from adresses
```
![delete](https://user-images.githubusercontent.com/77542685/204291159-7a4263d9-591b-442b-98fb-a0f323c3503d.png)

# ---------------------------------InnerJoin--------------------------------
```sql
--Bir müşterinin siparişlerini hangi bankayla ödendediğini göster
Select first_name, last_name,bank_name
From customers cm
Inner Join orders ord 
on cm.customer_id = ord.customer_id 
Inner join payments pa
on ord.order_id = pa.order_id
Where first_name = 'aytekin'
```
![batu](https://user-images.githubusercontent.com/77542685/204290302-4e4c0dca-f557-4500-804e-09646014130c.png)
# ---------------------------------FullOuterJoin-----------------------------
```sql
--Customer ile Orders tablosunun çıktılarını hep beraber al (full outer join)
select * from Customers cm full outer join Orders ord 
on cm.customer_id = ord.customer_id ;
```
![all](https://user-images.githubusercontent.com/77542685/204292572-ce7e545d-e84c-416b-bb51-5f5f7c8111ac.png)
# ---------------------------------LeftJoin-----------------------------
```sql
--Alıcısı belli olmayan siparişleri getirmeyen sorgu (Left Join)
select * from Customers cm left join Orders ord 
on cm.customer_id = ord.customer_id
```
![alll](https://user-images.githubusercontent.com/77542685/204292981-940a0e8b-965b-4e70-91ae-c9fab56139cb.png)
# ---------------------------------RightJoin-----------------------------
```sql
--Ürünü belli olup alıcısı belli olmayan siperişleri de getiren sorgu (Right join)
select * from Customers cm RIGHT join Orders ord 
on cm.customer_id = ord.customer_id 
```
![all](https://user-images.githubusercontent.com/77542685/204293354-60bf5d14-446c-47bf-a892-a365bc464825.png)
# ---------------------------------GroupBy-----------------------------
```sql
--Şehirlerde kaç adet kayıtlı kullanıcı olduğunu gösterir.
select city_name,count(city_name)
From customers cm
Inner join addresses ad
on cm.customer_id = ad.customer_id 
Inner join cities ci
ON ad.city_id = ci.city_id
group by city_name
```
![city](https://user-images.githubusercontent.com/77542685/204294047-88360035-2167-431d-9f8c-ceaac4da4948.png)
# ---------------------------------------------------------------------------
