# ac-a25-mysql-fake-data
分享給AC同學用的A25假資料

## How-to-use
把下方程式碼複製貼上到
http://sqlfiddle.com/
點選Build Schema就可以作為配合A25作業測試用的資料庫

結構與教案應該是一樣的
drinks, customers, orders共三個tables
每個table的主鍵都是id
其中orders包含drink_id, customer_id兩個外鍵

![ERD](https://github.com/EasonLin0716/ac-a25-mysql-fake-data/blob/master/A25.png)

有錯誤的話在提醒我一下，希望可以幫到大家，謝謝
```

CREATE TABLE `drinks` (
`id` INT unsigned NOT NULL AUTO_INCREMENT,
`name` VARCHAR(20) NOT NULL,
`price` INT unsigned NOT NULL,
`cost` INT unsigned NOT NULL,
PRIMARY KEY (`id`)
);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('阿華田', 65, 20);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('百香紅茶', 45, 10);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('四季春茶', 25, 5);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('愛玉冰茶', 50, 7);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('冰咖啡', 70, 30);

INSERT INTO `drinks` (`name`, `price`, `cost`)
VALUES ('青椒紅茶', 40, 10);

CREATE TABLE `customers` (
`id` INT unsigned NOT NULL AUTO_INCREMENT,
`name` VARCHAR(20) NOT NULL,
`phone number` VARCHAR(20) NOT NULL,
`birthday` DATE NOT NULL,
PRIMARY KEY (`id`)
);

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Steve Rogers', '0988123123', '1997-10-22');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Tony Stark', '0912878787', '1993-04-28');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Thor Odinson', '0933456789', '1991-06-12');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Natasha', '0912872332', '1996-02-05');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Clint Barton', '0978123223', '1976-11-20');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Bruce Banner', '0933444555', '1983-03-12');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Sam Wilson', '0956558777', '1987-03-13');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Peter Quill', '0933000999', '1972-01-03');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Stephen Strange', '0983223443', '1967-09-08');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Wong', '0933666777', '1934-06-30');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('TChalla', '0913444333', '1967-08-08');

INSERT INTO `customers` (`name`, `phone number`, `birthday`)
VALUES ('Peter Parker', '0955444333', '1999-01-08');

CREATE TABLE `orders` (
    `id` INT unsigned NOT NULL AUTO_INCREMENT,
    `drink_id` INT unsigned NOT NULL,
    `customer_id` INT unsigned NOT NULL,
    `quantity` INT unsigned NOT NULL,
    `created_date` DATETIME NOT NULL,
    PRIMARY KEY (`id`),
    FOREIGN KEY (`drink_id`) REFERENCES `drinks` (`id`),
    FOREIGN KEY (`customer_id`) REFERENCES `customers` (`id`)
);

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('1', '2', '4', '2019-10-01 09:29:42');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '2', '3', '2019-10-01 09:30:56');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('3', '2', '9', '2019-10-01 10:19:27');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('3', '1', '2', '2019-10-01 10:12:08');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '3', '4', '2019-10-01 10:42:36');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('1', '4', '3', '2019-10-01 10:56:08');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '4', '3', '2019-10-01 11:05:15');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('5', '1', '3', '2019-10-01 11:08:09');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '5', '4', '2019-10-01 11:11:11');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('3', '5', '3', '2019-10-01 12:33:34');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '6', '3', '2019-10-01 13:23:02');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('3', '7', '1', '2019-10-01 14:37:12');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('3', '8', '4', '2019-10-01 14:39:24');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '9', '4', '2019-10-01 14:49:42');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('2', '10', '3', '2019-10-01 15:00:00');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('1', '11', '3', '2019-10-01 15:00:12');

INSERT INTO `orders` (`drink_id`, `customer_id`, `quantity`, `created_date`)
VALUES ('1', '12', '2', '2019-10-01 15:05:06');

```
