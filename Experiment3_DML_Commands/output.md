**Question 1**
--
![image](https://github.com/user-attachments/assets/3b319c53-1884-4192-adb0-72066b11b01d)



```sql
update Customer
set grade=5
where city='Chennai';
```

**Output:**

![image](https://github.com/user-attachments/assets/ea3d3a7b-679e-4e26-80ef-828994985a2f)



**Question 2**
---
![image](https://github.com/user-attachments/assets/76fe1896-dc20-4ea2-95df-54a04ebbc052)


```sql
update products
set sell_price=sell_price*1.10
where category = 'Bakery';
```

**Output:**

![image](https://github.com/user-attachments/assets/162bc718-90b1-4eb8-b024-f456e1e7b415)


**Question 3**
---
![image](https://github.com/user-attachments/assets/bbf1247c-7d64-4a12-8371-7e9c71d7784a)


```sql
update products
set reorder_lvl=reorder_lvl*1.3
where category='Food'and quantity<reorder_lvl*0.5;
```

**Output:**

![image](https://github.com/user-attachments/assets/0278a412-1fed-419e-8921-f9b44b2d58dd)


**Question 4**
---
![image](https://github.com/user-attachments/assets/e1caa79b-60eb-4719-89b8-f9da0ed5b629)


```sql
update employees
set first_name='John'
where department_id=80 and
commission_pct<0.35;
```

**Output:**

![image](https://github.com/user-attachments/assets/fe9a8ee6-d6dc-49e3-8f99-dc6ffa63f6ac)


**Question 5**
---
![image](https://github.com/user-attachments/assets/bf8ef655-9420-460f-a82c-bdb4ddf3005e)

```sql
update suppliers
set supplier_name=
upper(supplier_name)
where contact_person like '%Singh%';
```

**Output:**

![image](https://github.com/user-attachments/assets/fbdea183-1fcb-4bc7-a08e-eba465e990d7)


**Question 6**
---
![image](https://github.com/user-attachments/assets/db00dbfb-31b0-43cc-bb25-b662509fee81)


```sql
delete from customer
where cust_city like 'L%';
```

**Output:**

![image](https://github.com/user-attachments/assets/e4f131a2-2d6c-4d94-81e9-8209126644d8)


**Question 7**
---
![image](https://github.com/user-attachments/assets/adf55a45-c8a4-4e46-9147-b7c68bfb2e45)


```sql
delete from customer
where length(cust_name)=6;
```

**Output:**

![image](https://github.com/user-attachments/assets/7d77cb56-231a-48e9-bffe-b292360da117)


**Question 8**
---
![image](https://github.com/user-attachments/assets/f485e042-0145-41f5-bf0e-189426a34f7c)


```sql
delete from surgeries
where surgery_id=3 or surgeon_id=4;
```

**Output:**

![image](https://github.com/user-attachments/assets/bd103503-2adc-490e-88df-f999610e41f9)


**Question 9**
---
![image](https://github.com/user-attachments/assets/88d2e4ae-2e57-4fc9-af36-ee09201792cf)


```sql
delete from doctors
where doctor_id between 2 and 4;
```

**Output:**

![image](https://github.com/user-attachments/assets/bbe1f4ec-aad8-48e0-aee1-9379c6486b08)


**Question 10**
---
![image](https://github.com/user-attachments/assets/c3f80b64-2e77-4aca-9d41-73786358ee12)


```sql
delete from Customer
where (GRADE > 2 and PAYMENT_AMT <(select avg(PAYMENT_AMT) from Customer))
    or OUTSTANDING_AMT>8000;
```

**Output:**

![image](https://github.com/user-attachments/assets/6309efab-c5c1-4d56-976d-87acdea01c84)

