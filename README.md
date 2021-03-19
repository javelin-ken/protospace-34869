# テーブル設計

# usersテーブル

| Column     | Type   | Option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototypes
- has_many :comments


# prototypesテーブル

| Column     | Type          | Option      |
| ---------- | ------------- | ----------- |
| title      | string        | null: false |
| catch_copy | text          | null: false |
| concept    | text          | null: false |
| image      | ActiveStorage |             |
| user       | references    |             | 

### Association

- has_many :comments
- belongs_to :user



# commentsテーブル

| Column    | Type       | Option     |
| --------- | ---------- | ---------- |
| text      | text       | text       | 
| user      | references | references |
| prototype | references | references |

### Association

- belongs_to :prototype
- belongs_to :user