-- ============================================================
--  Aphelion Tea — Management System
--  Database: aphelion_tea
--  Import via phpMyAdmin: Database > Import > pilih file ini
-- ============================================================

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+07:00";

-- Buat database
CREATE DATABASE IF NOT EXISTS `aphelion_tea`
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;

USE `aphelion_tea`;

-- ============================================================
-- TABLE: users
-- ============================================================
CREATE TABLE IF NOT EXISTS `users` (
  `id`          INT(11)      NOT NULL AUTO_INCREMENT,
  `name`        VARCHAR(100) NOT NULL,
  `username`    VARCHAR(50)  NOT NULL UNIQUE,
  `password`    VARCHAR(255) NOT NULL COMMENT 'bcrypt hash',
  `role`        ENUM('admin','staff') NOT NULL DEFAULT 'staff',
  `booth_id`    INT(11)      DEFAULT NULL,
  `phone`       VARCHAR(20)  DEFAULT NULL,
  `email`       VARCHAR(100) DEFAULT NULL,
  `address`     TEXT         DEFAULT NULL,
  `join_date`   DATE         DEFAULT (CURDATE()),
  `active`      TINYINT(1)   NOT NULL DEFAULT 1,
  `created_at`  DATETIME     NOT NULL DEFAULT CURRENT_TIMESTAMP,
  `updated_at`  DATETIME     NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `idx_username` (`username`),
  KEY `idx_role`     (`role`),
  KEY `idx_booth`    (`booth_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- TABLE: booths
-- ============================================================
CREATE TABLE IF NOT EXISTS `booths` (
  `id`          INT(11)      NOT NULL AUTO_INCREMENT,
  `name`        VARCHAR(100) NOT NULL,
  `location`    VARCHAR(200) DEFAULT NULL,
  `pic`         VARCHAR(100) DEFAULT NULL COMMENT 'Penanggung Jawab',
  `active`      TINYINT(1)   NOT NULL DEFAULT 1,
  `created_at`  DATETIME     NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- TABLE: flavors
-- ============================================================
CREATE TABLE IF NOT EXISTS `flavors` (
  `id`          INT(11)      NOT NULL AUTO_INCREMENT,
  `name`        VARCHAR(100) NOT NULL,
  `icon`        VARCHAR(10)  DEFAULT '🍵',
  `price`       INT(11)      NOT NULL DEFAULT 0,
  `active`      TINYINT(1)   NOT NULL DEFAULT 1,
  `created_at`  DATETIME     NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- TABLE: stock  (stok per booth per rasa)
-- ============================================================
CREATE TABLE IF NOT EXISTS `stock` (
  `id`          INT(11)   NOT NULL AUTO_INCREMENT,
  `booth_id`    INT(11)   NOT NULL,
  `flavor_id`   INT(11)   NOT NULL,
  `qty`         INT(11)   NOT NULL DEFAULT 0,
  `updated_at`  DATETIME  NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `uq_booth_flavor` (`booth_id`,`flavor_id`),
  KEY `idx_booth`  (`booth_id`),
  KEY `idx_flavor` (`flavor_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- TABLE: transactions
-- ============================================================
CREATE TABLE IF NOT EXISTS `transactions` (
  `id`          INT(11)      NOT NULL AUTO_INCREMENT,
  `booth_id`    INT(11)      NOT NULL,
  `payment`     ENUM('cash','qris') NOT NULL DEFAULT 'cash',
  `total`       INT(11)      NOT NULL DEFAULT 0,
  `tx_date`     DATE         NOT NULL DEFAULT (CURDATE()),
  `tx_time`     TIME         NOT NULL DEFAULT (CURTIME()),
  `created_by`  INT(11)      DEFAULT NULL COMMENT 'user id kasir',
  `created_at`  DATETIME     NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `idx_booth`  (`booth_id`),
  KEY `idx_date`   (`tx_date`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- TABLE: transaction_items
-- ============================================================
CREATE TABLE IF NOT EXISTS `transaction_items` (
  `id`          INT(11)  NOT NULL AUTO_INCREMENT,
  `tx_id`       INT(11)  NOT NULL,
  `flavor_id`   INT(11)  NOT NULL,
  `qty`         INT(11)  NOT NULL DEFAULT 1,
  `price`       INT(11)  NOT NULL DEFAULT 0,
  PRIMARY KEY (`id`),
  KEY `idx_tx`     (`tx_id`),
  KEY `idx_flavor` (`flavor_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- ============================================================
-- FOREIGN KEYS
-- ============================================================
ALTER TABLE `users`
  ADD CONSTRAINT `fk_users_booth`
    FOREIGN KEY (`booth_id`) REFERENCES `booths`(`id`) ON DELETE SET NULL;

ALTER TABLE `stock`
  ADD CONSTRAINT `fk_stock_booth`
    FOREIGN KEY (`booth_id`) REFERENCES `booths`(`id`) ON DELETE CASCADE,
  ADD CONSTRAINT `fk_stock_flavor`
    FOREIGN KEY (`flavor_id`) REFERENCES `flavors`(`id`) ON DELETE CASCADE;

ALTER TABLE `transactions`
  ADD CONSTRAINT `fk_tx_booth`
    FOREIGN KEY (`booth_id`) REFERENCES `booths`(`id`),
  ADD CONSTRAINT `fk_tx_user`
    FOREIGN KEY (`created_by`) REFERENCES `users`(`id`) ON DELETE SET NULL;

ALTER TABLE `transaction_items`
  ADD CONSTRAINT `fk_txi_tx`
    FOREIGN KEY (`tx_id`) REFERENCES `transactions`(`id`) ON DELETE CASCADE,
  ADD CONSTRAINT `fk_txi_flavor`
    FOREIGN KEY (`flavor_id`) REFERENCES `flavors`(`id`);

-- ============================================================
-- SEED DATA — Booths
-- ============================================================
INSERT INTO `booths` (`id`,`name`,`location`,`pic`,`active`) VALUES
(1,'Booth Alun-alun','Alun-alun Kota','Siti Rahayu',1),
(2,'Booth Pasar Seni','Pasar Seni Lama','Budi Santoso',1),
(3,'Booth Kampus','Depan Kampus Barat','Dewi Puspita',1);

-- ============================================================
-- SEED DATA — Flavors
-- ============================================================
INSERT INTO `flavors` (`id`,`name`,`icon`,`price`) VALUES
(1,'Teh Lemon Original','🍋',8000),
(2,'Teh Lychee','🍈',9000),
(3,'Teh Strawberry','🍓',9000),
(4,'Teh Passion Fruit','🟡',10000),
(5,'Teh Peach','🍑',10000),
(6,'Teh Matcha','🍵',11000),
(7,'Teh Taro','🫐',11000),
(8,'Teh Original Tawar','🫖',7000);

-- ============================================================
-- SEED DATA — Stock
-- ============================================================
INSERT INTO `stock` (`booth_id`,`flavor_id`,`qty`) VALUES
(1,1,40),(1,2,25),(1,3,30),(1,4,20),(1,5,15),(1,6,18),(1,7,12),(1,8,50),
(2,1,35),(2,2,20),(2,3,22),(2,4,18),(2,5,20),(2,6,10),(2,7,8),(2,8,40),
(3,1,50),(3,2,30),(3,3,28),(3,4,25),(3,5,22),(3,6,15),(3,7,10),(3,8,60);

-- ============================================================
-- SEED DATA — Users  (password = bcrypt dari string di bawah)
--   admin   → admin123
--   staff   → pass123
-- Generate ulang hash di PHP: password_hash('admin123', PASSWORD_BCRYPT)
-- ============================================================
INSERT INTO `users` (`id`,`name`,`username`,`password`,`role`,`booth_id`,`phone`,`email`,`address`,`join_date`,`active`) VALUES
(1,'Administrator','admin',
  '$2y$10$92IXUNpkjO0rOQ5byMi.Ye4oKoEa3Ro9llC/.og/at2uheWG/igi.',
  'admin',NULL,'081234567890','admin@apheliontea.id','Jl. Merdeka No. 1, Kota','2024-01-01',1),
(2,'Siti Rahayu','booth1',
  '$2y$10$TKh8H1.PsgDq48y6mRfOuOLWQkP.wHJNvIeUSZa97kePRHETBSi1S',
  'staff',1,'082233445566','siti@apheliontea.id','Jl. Melati No. 12, Pasuruan','2024-03-15',1),
(3,'Budi Santoso','booth2',
  '$2y$10$TKh8H1.PsgDq48y6mRfOuOLWQkP.wHJNvIeUSZa97kePRHETBSi1S',
  'staff',2,'083344556677','budi@apheliontea.id','Jl. Anggrek No. 5, Pasuruan','2024-03-20',1),
(4,'Dewi Puspita','booth3',
  '$2y$10$TKh8H1.PsgDq48y6mRfOuOLWQkP.wHJNvIeUSZa97kePRHETBSi1S',
  'staff',3,'084455667788','dewi@apheliontea.id','Jl. Mawar No. 8, Pasuruan','2024-04-01',1);

-- ============================================================
-- SEED DATA — Transactions (sample hari ini)
-- ============================================================
INSERT INTO `transactions` (`id`,`booth_id`,`payment`,`total`,`tx_date`,`tx_time`,`created_by`) VALUES
(1,1,'cash',24000,CURDATE(),'08:15:00',2),
(2,2,'qris',18000,CURDATE(),'09:00:00',3),
(3,1,'cash',11000,CURDATE(),'09:30:00',2),
(4,3,'qris',36000,CURDATE(),'10:00:00',4),
(5,2,'cash',28000,CURDATE(),'10:45:00',3),
(6,3,'qris',40000,CURDATE(),'11:00:00',4),
(7,1,'cash',20000,CURDATE(),'11:30:00',2),
(8,2,'qris',11000,CURDATE(),'12:00:00',3);

INSERT INTO `transaction_items` (`tx_id`,`flavor_id`,`qty`,`price`) VALUES
(1,1,3,8000),
(2,3,2,9000),
(3,6,1,11000),
(4,2,4,9000),
(5,5,2,10000),(5,1,1,8000),
(6,1,5,8000),
(7,4,2,10000),
(8,7,1,11000);

-- ============================================================
-- VIEWS (opsional — mempermudah query laporan)
-- ============================================================
CREATE OR REPLACE VIEW `v_daily_revenue` AS
SELECT
  t.tx_date,
  b.name AS booth_name,
  COUNT(t.id) AS total_tx,
  SUM(ti.qty) AS total_qty,
  SUM(t.total) AS revenue,
  SUM(CASE WHEN t.payment='cash' THEN t.total ELSE 0 END) AS cash_revenue,
  SUM(CASE WHEN t.payment='qris' THEN t.total ELSE 0 END) AS qris_revenue
FROM transactions t
JOIN booths b ON b.id = t.booth_id
JOIN transaction_items ti ON ti.tx_id = t.id
GROUP BY t.tx_date, t.booth_id;

CREATE OR REPLACE VIEW `v_stock_summary` AS
SELECT
  s.booth_id,
  b.name  AS booth_name,
  s.flavor_id,
  f.name  AS flavor_name,
  f.icon  AS flavor_icon,
  f.price,
  s.qty
FROM stock s
JOIN booths  b ON b.id = s.booth_id
JOIN flavors f ON f.id = s.flavor_id;
