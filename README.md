# テーブル設計

##  users テーブル

| Column     | Type   | Options      |
| ---------- | ------ | ------------ |
| email      | string | NOT NULL     | 
| password   | string | NOT NULL     | 
| name       | string | NOT NULL     | 
| profile    | text   | NOT NULL     | 
| occupation | text   | NOT NULL     | 
| position   | text   | NOT NULL     | 

## Association

-has_many  :prototype
-has_many  :comment

##  prototype テーブル

| Column     | Type       | Options      |
| ---------- | ---------- | ------------ |
| title      | string     | NOT NULL     | 
| catch_copy | text       | NOT NULL     | 
| concept    | text       | NOT NULL     | 
| user       | references |              | 

## Association

-has_many  :comments
-has_many  :users

## comments テーブル

| Column    | Type       | Options      |
| --------- | ---------- | ------------ |
| text      | text       | NOT NULL     | 
| user      | references |              | 
| prototype | references |              |

## Association
 -belongs_to  :user
 -belongs_to  :prototype 