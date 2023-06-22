# SQL_DDL
Первая часть.


# Таблица employees
Создать таблицу employees
- id. serial,  primary key,
- employee_name. Varchar(50), not null
```
create table  employees (
id serial primary key,
employee_name Varchar(50) not null
);
```
Наполнить таблицу employee 70 строками.
```
insert into employees(employee_name)
values ('Mark Nash'),
('Samantha Kingfisher'),
('Richard Faulkner'),
('Fiona Yeoman'),
('Henry Earl'),
('Julia Wrapson'),
('Geoffrey Keating'),
('Barbara Mulgroon'),
('Frederick Dylan'),
('Helen Pendrick'),
('Mark Trussell'),
('Bethany Andrews'),
('James Richards'),
('Shirley Randall'),
('Benjamin Newbry'),
('Melissa Caine'),
('Gregory James'),
('Judy Tasker'),
('Desmond Potter'),
('Yasmin Gilbert'),
('William Barton'),
('Diana Elerick'),
('George Hanwell'),
('Irene Ellis'),
('Raymond Edwards'),
('Kelly Randall'),
('Yusef Boyes'),
('Rachel Houston'),
('Phillip Allen'),
('Melissa Hadden'),
('Carl Tattershall'),
('Laura Moore'),
('Christian Samuel'),
('Hannah Eckard'),
('Keith Tackett'),
('Kelly Crocket'),
('Craig Walker'),
('Margaret Salisbury'),
('Thomas Raymond'),
('Emily Tattershall'),
('Jamie Unsworth'),
('Zelda Dooley'),
('Matthew Dorsey'),
('Leah Ingeman'),
('Darryl Smith'),
('Jessica Abraham'),
('Simon Rathbone'),
('Laura Haines'),
('William Jarvis'),
('Rose Patrick'),
('Kenneth Ramsey'),
('Bethany Pattishal'),
('Jack Ackroyd'),
('Stacy Ward'),
('Edward Haines'),
('Julia Coxon'),
('Christopher Marshall'),
('Ruth Taylor'),
('Roger Ramsey'),
('Geraldine Rawlinson'), 
('Gordon Wyatt'), 
('Deborah Holloway'), 
('George Rathbone'), 
('Eleanor Kingston'), 
('Alexander Sadler'), 
('Julia Halsall'), 
('Gregory Macarthur'), 
('Violet Santini'), 
('Alexander Portillo'), 
('Susan Porter')
;

```
# Таблица salary
Создать таблицу salary
- id. Serial  primary key,
- monthly_salary. Int, not null
```
create table salary (
id serial primary key,
monthly_salary Int not null
);
```
Наполнить таблицу salary 15 строками:
```
insert into salary (monthly_salary)
values
(1000),
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
Создать таблицу employee_salary
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
```
create table employee_salary (
id serial primary key,
employee_id Int unique not null,
salary_id Int not null
);
```
Наполнить таблицу employee_salary 40 строками:
- в 10 строк из 40 вставить несуществующие employee_id
```
insert into employee_salary (employee_id, salary_id) 
values 
		(71, 10),
		(60, 11),
		(72, 12),
		(55, 13),
		(73, 14),
		(50, 15),
		(74, 16),
		(48, 1),
		(75, 2),
		(44, 3),
		(76, 4),
		(40, 5),
		(77, 6),
		(35, 7),
		(78, 8),
		(33, 9),
		(79, 10),
		(30, 11),
		(80, 12),
		(28, 13),
		(27, 14),
		(25, 15),
		(11, 16),
		(23, 15),
		(13, 14),
		(15, 13),
		(18, 12),
		(20, 11),
		(21, 10),
		(22, 9),
		(24, 8)
		;
```
# Таблица roles
Создать таблицу roles
- id. Serial  primary key,
- role_name. int, not null, unique
```
create table roles (
id serial primary key,
role_name Int unique not null
);
```
Поменять тип столба role_name с int на varchar(30)
```
alter table roles
alter column role_name type
varchar(30)
;
```
Наполнить таблицу roles 20 строками:
```
insert into roles (role_name)
values ('Junior Python developer'),
('Middle Python developer'),
('Senior Python developer'),
('Junior Java developer'),
('Middle Java developer'),
('Senior Java developer'),
('Junior JavaScript developer'),
('Middle JavaScript developer'),
('Senior JavaScript developer'),
('Junior Manual QA engineer'),
('Middle Manual QA engineer'),
('Senior Manual QA engineer'),
('Project Manager'),
('Designer'),
('HR'),
('CEO'),
('Sales manager'),
('Junior Automation QA engineer'),
('Middle Automation QA engineer'),
('Senior Automation QA engineer')
;
```
# Таблица roles_employee
Создать таблицу roles_employee
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
```
create table roles_employee (
id serial primary key,
employee_id Int unique not null,
role_id Int not null,
foreign key (employee_id) references employees (id),
foreign key (role_id) references  roles (id)
);
```
Наполнить таблицу roles_employee 40 строками:
```
insert into roles_employee (employee_id, role_id)
values (20, 1),
(31, 19),
(19, 2),
(33, 18),
(18, 3),
(35, 17),
(17, 4),
(37, 16),
(16, 5),
(39, 15),
(15, 6),
(41, 14),
(14, 7),
(43, 13),
(13, 8),
(45, 12),
(12, 9),
(47, 11),
(11, 10),
(49, 1),
(10, 3),
(52, 5),
(9, 7),
(54, 9),
(8, 11),
(56, 13),
(7, 15),
(58, 17),
(6, 19),
(60, 20),
(5, 16),
(62, 14),
(4, 12),
(64, 10),
(3, 9),
(66, 8),
(2, 7),
(68, 6),
(1, 5),
(70, 4)
;

```







