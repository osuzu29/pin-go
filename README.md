# テーブル設計

## users テーブル(ユーザー情報)

| Column             | Type       | Options                   |
|--------------------|------------|---------------------------|
| nickname           | string     | null: false               |
| email              | string     | null: false, unique: true |
| encrypted_password | string     | null: false               |

### Association

- has_many :places

## Places テーブル(行きたい場所)

| Column           | Type       |Options                         |
|------------------|------------|---------------------------- ---|
| name             | string     | null: false                    |
| address          | string     | null: false                    |
| latitude         | float      | null: false                    |
| longitude        | float      | null: false                    |
| category_id      | integer    | null: false                    |
| label_id         | integer    | null: false                    |
| instagram_url    | string     | null: false                    |
| visited_id       | integer    | null: false                    |
| user             | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :photos


## Photos テーブル(写真記録)

| Column     | Type       | Options                        |
|------------|------------|--------------------------------|
| place      | references | null: false, foreign_key: true |
| image      | string     | null: false, foreign_key: true |


### Association

- belongs_to :place