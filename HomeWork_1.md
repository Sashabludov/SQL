# Таблица employees
## Создать таблицу employees
 - id. serial,  primary key,
 - employee_name. Varchar(50), not null
```
create table employees(
id serial  primary key,
	employee_name Varchar(50) not null
);
```

## Наполнить таблицу employee 70 строками.
```
insert into employees(employee_name)
values ('Maisie Casey'),
  ('Deacon Wright'),
  ('Colette Chang'),
  ('Charlotte Kerr'),
  ('Christine Roth'),
  ('Curran Perkins'),
  ('Marshall Evans'),
  ('Adrian Franks'),
  ('Zahir Hayden'),
  ('Britanni Graham'),
  ('Graham Velazquez'),
  ('Meghan Lester'),
  ('Ulla Orr'),
  ('Jaime Mayo'),
  ('Ori Rose'),
  ('Lunea Parker'),
  ('Summer Hale'),
  ('Nora Strickland'),
  ('Burton Rowe'),
  ('Miriam Tyler'),
  ('Fletcher Velez'),
  ('Justine Wooten'),
  ('Martin Mcdaniel'),
  ('Damian Osborne'),
  ('Jesse Potter'),
  ('Lysandra Dickerson'),
  ('Fleur Carpenter'),
  ('Brenden Francis'),
  ('Destiny Crosby'),
  ('Cynthia Harper'),
  ('Damon Sandoval'),
  ('Logan Noel'),
  ('Alan England'),
  ('Sarah Sandoval'),
  ('Trevor Holloway'),
  ('Kenneth Velasquez'),
  ('Nigel Sanchez'),
  ('Kamal Daniels'),
  ('Molly Burris'),
  ('Keelie Jarvis'),
  ('Brady Joyce'),
  ('Amal Hale'),
  ('Jameson Preston'),
  ('Keelie Richards'),
  ('Mollie Perez'),
  ('Jameson Dejesus'),
  ('Carolyn Bryant'),
  ('Silas Jensen'),
  ('Rooney Gomez'),
  ('Carol Burton');
```
# Таблица salary
## Создать таблицу salary
- id. Serial  primary key,
- monthly_salary. Int, not null
```
create table salary(
	id serial primary key,
	monthly_salary int not null
);
```

## Наполнить таблицу salary 15 строками
```
insert into salary (monthly_salary)
values (1000),
	   (1100),
	   (1200),
	   (1300),
 	   (1400),
	   (1500),
 	   (1600),
 	   (1700),
 	   (1800),
 	   (1900),
	   (2000),
 	   (2100),
 	   (2200),
 	   (2300),
           (2400),
 	   (2500);
```

# Таблица employee_salary
## Создать таблицу employee_salary
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
```
create table employee_salary(
	id serial primary key,
	employee_id int not null unique,
	salary_id int not null
);
```

## Наполнить таблицу employee_salary 40 строками:
- в 10 строк из 40 вставить несуществующие employee_id
  ```
  insert into employee_salary(employee_id, salary_id)
  values (51, 1), (52, 2), (53, 3), (54, 4), (55, 5), (56, 6), (57, 7), (58, 8), (59, 9), (60, 10),
         (1, 1), (2, 2), (3, 3), (4, 4), (5, 5), (6, 6), (7, 7), (8, 8), (9, 9), (10, 10),
         (11, 11), (12, 12), (13, 13), (14, 14), (15, 15), (16, 16), (17, 13), (18, 12), (19, 11), (20, 15),
         (21, 11), (22, 12), (23, 13), (24, 14), (25, 15), (26, 16), (27, 13), (28, 12), (29, 11), (30, 5);
    ```

# Таблица roles
## Создать таблицу roles
- id. Serial  primary key,
- role_name. int, not null, unique
```
create table roles(
	id serial primary key,
	role_name int not null unique
);
```
## Поменять тип столба role_name с int на varchar(30)
```
alter table roles
alter column role_name type varchar(30);
```
## Наполнить таблицу roles 20 строками:
```
insert into roles(role_name)
values ('Junior Python developer'), ('Middle Python developer'), ('Senior Python developer'),
  ('Junior Java developer'), ('Middle Java developer'), ('Senior Java developer'),
  ('Junior JavaScript developer'), ('Middle JavaScript developer'), ('Senior JavaScript developer'),
  ('Junior Manual QA engineer'), ('Middle Manual QA engineer'), ('Senior Manual QA engineer'),
  ('Project Manager'), ('Designer'), ('HR'), ('CEO'), ('Sales manager'),
  ('Junior Automation QA engineer'), ('Middle Automation QA engineer'), ('Senior Automation QA engineer');
```

# Таблица roles_employee
## Создать таблицу roles_employee
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
```
create table roles_employee(
	id serial primary key,
	employee_id int not null unique references employees (id),
	role_id int not null references roles (id)
  );
```


# Наполнить таблицу roles_employee 40 строками:
```
insert into roles_employee (employee_id, role_id)
values (41, 1), (42, 2), (43, 3), (44, 4), (45, 5), (46, 6), (47, 7), (48, 8), (49, 9), (50, 20),
       (1, 9), (2, 20), (3, 3), (4, 4), (5, 18), (6, 6), (7, 7), (8, 18), (9, 18), (10, 10),
       (11, 11), (12, 19), (13, 17), (14, 14), (15, 15), (16, 16), (17, 13), (18, 12), (19, 11), (20, 15),
       (21, 11), (22, 12), (23, 13), (24, 14), (25, 17), (26, 16), (27, 19), (28, 18), (29, 17), (30, 16);
```
