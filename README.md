# MYSQL-IMDB

My Sql task

IMDB Design a DB for IMDB 
1. Movie should have multiple media(Video or Image) 
2. Movie can belongs to multiple Genre 
3. Movie can have multiple reviews and Review can belongs to a user 
4. Artist can have multiple skills
 5. Artist can perform multiple role in a single film



SOLUTION:

-- create database imdb
-- use imdb
-- CREATE TABLE Movies (
--   movie_id 	VARCHAR(255) NOT NULL,
--   movie_title VARCHAR(255) NOT NULL,
--   movie_year int NOT NULL,
--   movie_lang varchar(255),
--   PRIMARY KEY (movie_id)
-- );

-- ALTER TABLE Movies
-- DROP COLUMN movie_lang;
-- INSERT INTO `imdb`.`Movies` (`movie_id`, `movie_title`, `movie_year`) VALUES ('101', 'ENTHIRAN', '2010');

-- CREATE TABLE Genres (
-- 	id int not null auto_increment,
-- 	movie_id 	VARCHAR(255) NOT NULL,
-- 	movie_genre varchar(255),
--     PRIMARY KEY (id),
--     FOREIGN KEY (movie_id) REFERENCES Movies(movie_id)
-- );










-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
-- -----------------------------------------------------
-- Schema imdb
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema imdb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `imdb` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
USE `imdb` ;

-- -----------------------------------------------------
-- Table `imdb`.`movies`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `imdb`.`movies` (
  `movie_id` VARCHAR(255) NOT NULL,
  `movie_title` VARCHAR(255) NOT NULL,
  `movie_year` INT NOT NULL,
  PRIMARY KEY (`movie_id`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8mb4
COLLATE = utf8mb4_0900_ai_ci;


-- -----------------------------------------------------
-- Table `imdb`.`genres`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `imdb`.`genres` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `movie_id` VARCHAR(255) NOT NULL,
  `movie_genre` VARCHAR(255) NULL DEFAULT NULL,
  PRIMARY KEY (`id`),
  INDEX `movie_id` (`movie_id` ASC) VISIBLE,
  CONSTRAINT `genres_ibfk_1`
    FOREIGN KEY (`movie_id`)
    REFERENCES `imdb`.`movies` (`movie_id`))
ENGINE = InnoDB
AUTO_INCREMENT = 2
DEFAULT CHARACTER SET = utf8mb4
COLLATE = utf8mb4_0900_ai_ci;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;






