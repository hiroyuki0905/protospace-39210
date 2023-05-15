DB設計

## User_table 
| Column            | Type      |    Option                     |
|-------------------|-------------------------------------------|
|email              | string    |    null: false, unique: true  |
|-------------------|-------------------------------------------|
|encrypted_password | string    |    null: false                |
|-------------------|-------------------------------------------|
|name               | string    |    null: false                |
|-------------------|-------------------------------------------|
|profile            | text      |    null: false                |
|-------------------|-------------------------------------------|
|occupation         | text      |    null: false                |
|-------------------|-------------------------------------------|
|position           | text      |    null: false                |
### Association 
- has_many : Comments_table
- has_many : Prototype_table


## Comments_table
| Column            | Type       |    Option
|-------------------|------------------------------------------------|
|content            | text       |    null: false                    |
|-------------------|------------------------------------------------|
|protype            | references |    null: false, foreign_key: true |
|-------------------|------------------------------------------------|
|user               | references |    null: false, foreign_key: true |
### Association
- belongs_to : Prototype_table
  belongs_to : User_table


## Prototype_table
| Column            | Type       |    Option
|-------------------|------------------------------------------------|
|title              | string     |    null: false                    |
|-------------------|------------------------------------------------|
|catch_copy         | text       |    null: false                    |
|-------------------|------------------------------------------------|
|user               | references |    null: false, foreign_key: true |
### Association
- belongs_to : User_table
- has_many : Comments_table