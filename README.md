# 環境構築手順

## DB作成
CREATE DATABASE kakeibo;

## テーブル作成
### categories
CREATE TABLE categories ( id int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY, name varchar(255) NOT NULL, user_id int(11) NOT NULL, created_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP, updated_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP);

### incomes
CREATE TABLE incomes (id int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY, user_id int(11) NOT NULL, income_source_id int(11) NOT NULL, amount int(11) NOT NULL, accrual_date date NOT NULL, created_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP, updated_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP);

### income_sources
CREATE TABLE income_sources (id int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY, name varchar(255) NOT NULL, user_id int(11) NOT NULL, created_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP, updated_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP);

### spendings
CREATE TABLE spendings (id int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY, name varchar(255) NOT NULL, user_id int(11) NOT NULL, category_id int(11) NOT NULL, amount int(11) NOT NULL, accrual_date date NOT NULL, created_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP, updated_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP);

### users
CREATE TABLE users (id int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY, email varchar(255) NOT NULL, password varchar(255) NOT NULL, created_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP, updated_at timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP);


## テストデータ
### users
INSERT INTO `users`(`id`, `email`, `password`) VALUES (1, 'test@gmail.com', 'testuser')