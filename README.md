# ModaMarket
Online Clothing Store
-- ************************************** `Product`

CREATE TABLE `Product`
(
 `id_Product`    integer NOT NULL AUTO_INCREMENT ,
 `name_Product`  varchar(45) NOT NULL ,
 `price_product` double NOT NULL ,
 `image`         varchar(115) NOT NULL ,
 `discount`      integer NOT NULL ,

PRIMARY KEY (`id_Product`)
);

-- ************************************** `Review`

CREATE TABLE `Review`
(
 `id_Review`   integer NOT NULL AUTO_INCREMENT ,
 `text_review` varchar(45) NOT NULL ,
 `id_Product`  integer NOT NULL ,
 `id_User`     integer NOT NULL ,

PRIMARY KEY (`id_Review`),
KEY `FK_1` (`id_Product`),
CONSTRAINT `FK_5` FOREIGN KEY `FK_1` (`id_Product`) REFERENCES `Product` (`id_Product`),
KEY `FK_2` (`id_User`),
CONSTRAINT `FK_6` FOREIGN KEY `FK_2` (`id_User`) REFERENCES `User` (`id_User`)
);


-- ************************************** `Order`

CREATE TABLE `Order`
(
 `id_order`   integer NOT NULL AUTO_INCREMENT ,
 `id_Product` integer NOT NULL ,
 `id_User`    integer NOT NULL ,

PRIMARY KEY (`id_order`),
KEY `FK_1` (`id_Product`),
CONSTRAINT `FK_1` FOREIGN KEY `FK_1` (`id_Product`) REFERENCES `Product` (`id_Product`),
KEY `FK_2` (`id_User`),
CONSTRAINT `FK_2` FOREIGN KEY `FK_2` (`id_User`) REFERENCES `User` (`id_User`)
);


-- ************************************** `User`

CREATE TABLE `User`
(
 `id_User`          integer NOT NULL AUTO_INCREMENT ,
 `first_name_User`  varchar(45) NOT NULL ,
 `last_name_User`   varchar(45) NOT NULL ,
 `dateofbirth_User` date NOT NULL ,
 `phone`            varchar(45) NOT NULL ,
 `email`            varchar(100) NOT NULL ,
 `adresse`          varchar(155) NOT NULL ,

PRIMARY KEY (`id_User`)
);
