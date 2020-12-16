# テーブル設計

## users テーブル

| Colum      | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association
has_many :prototypes
has_many :comments

## prototypes テーブル

| Colum      | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| image      |            |                                |
| user       | references | null: false, foreign_key: true |

### Association
has_many :comments
belongs_to :user

 ## comments テーブル

| Colum     | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

### Association
belongs_to :user
belongs_to :prototype

