<h1>
Примеры простых запросов SQL <img src="https://ultimateitcourses.ca/wp-content/uploads/2018/08/SQL.png" width="70">
</h1>
<h1>
 1. Создание таблицы категории товаров для женщин:
</h1>
CREATE TABLE `schema`.`categoties` (
  `categories_id` INT NOT NULL AUTO_INCREMENT,
  `categories_for_women` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`categories_id`));
  
  # Скриншот вызываемой таблицы из MySQL Workbench 8.0 CE
  Для вызова таблицы используется команда SELECT * FROM schema.categories;
  ![image](https://user-images.githubusercontent.com/108890950/182361340-d48fbfa5-443a-4e8c-b2a7-bd30d604ac88.png)

 # 2. Добавление данных в существующую таблицу:
 
 Для добавления данных в существующую таблицу используется команда 

 INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('--Категория товара--')
 
 
<!--INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Футболки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Шорты');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Бра');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Купальники');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Головные уборы');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Майки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Легинсы');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Платья');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Толстовки и худи');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Брюки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Юбки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Туники');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Бикини');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Рубашки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Поло');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Бриджи');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Костюмы');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Бельё');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Термобельё');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Носки и гетры');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Куртки');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Жилеты');
INSERT INTO `schema`.`categoties` (`categories_for_women`) VALUES ('Дождевики');-->

 # Скриншот добавленных данных из MySQL Workbench 8.0 CE
 
![image](https://user-images.githubusercontent.com/108890950/182361415-72f15e6d-cfe2-42f9-b86e-f26525640bcb.png)

 # 3. Создание таблицы с продукцией для женщин:
 
 CREATE TABLE `schema`.`product` (
  `product_id` INT NOT NULL AUTO_INCREMENT,
  `product_name` VARCHAR(45) NOT NULL,
  `manufacturer_id` INT NOT NULL,
  `categories_id` INT NOT NULL,
  `price` FLOAT NOT NULL,
  PRIMARY KEY (`product_id`));

 # Скриншот добавленных данных из MySQL Workbench 8.0 CE
 
  ![image](https://user-images.githubusercontent.com/108890950/182365348-7e27c57a-c64a-4602-a2b6-caaf999014b2.png)
  
 # 4. Выборка (WHERE):
 
 Для выбора товара с ценой меньше 500 руб, используется команда:
 
 SELECT * FROM schema.product WHERE price < 500;

 # Скриншот выбора данных из MySQL Workbench 8.0 CE
 
 ![image](https://user-images.githubusercontent.com/108890950/182365879-4e99308a-a945-49ee-bc98-c9a807115f74.png)
 
 # 5. Выборка c ограничениями(WHERE, ORDER BY):
 
 Для выбора товара с ценой менее 5000 руб, по порядку "от А до Я" - по убыванию цены, используется команда:
 
SELECT * FROM schema.product WHERE price < 5000 ORDER BY price DESC

# Скриншот выбора данных из MySQL Workbench 8.0 CE
 
![image](https://user-images.githubusercontent.com/108890950/182367334-15bb69a2-7018-43d6-9540-2fa999facb08.png)

# 6. Удаление строки:
 
 Для удаление строки кроссовки из таблицы categoies используется команда:
 
 DELETE FROM schema.categories WHERE categories_id = 24
 
# 7. Выборка с лимитом:

 Для выбора продуктов с лимитом, в наименовании которых присутствует значение "Футболка" используется команда:
 
 SELECT * FROM schema.product WHERE product_name LIKE '%Футболка%' LIMIT 10
 
 # Скриншот выбора данных из MySQL Workbench 8.0 CE
 
 ![image](https://user-images.githubusercontent.com/108890950/182369522-1f93be8c-6461-4244-8b01-9c96af4950b7.png)

С помощью данной команды удалось вывести максимальное количество футболкок внесенных в таблицу.
 
 
