# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | string | null: false |
| position   | text   | null: false |

### Association

- has_many :prototype
- has_many :comment

## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| image      |            |                                |
| user       | references | null: false, foreign_key: true |

### Association

- has_many :user
- has_many :comment

## comments テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| text       | text       | null: false                    |
| user       | references | null: false, foreign_key: true |
| prototype  | references | null: false, foreign_key: true |


### Association

- belongs_to :user
- belongs_to :prototype