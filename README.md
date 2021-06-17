# DB 設計

## users テーブル

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| nickname           | string              | null: false               |
| email              | string              | null: false, unique: true |
| encrypted_password | string              | null: false               |
| family_name        | string              | null: false               |
| first_name         | string              | null: false               |
| family_name_kana   | string              | null: false               |
| first_name_kana    | string              | null: false               |
| birth_day          | date                | null: false               |

### Association
- has_many: items
- belongs_to :buyer



## items テーブル

| Column             | Type                | Options                       |
|--------------------|---------------------|-------------------------------|
| product            | string              | null: false                   |
| introduction       | text                | null: false                   |
| category_id        | integer             | null: false                   |
| status_id          | integer             | null: false                   |
| burden_id          | integer             | null: false                   |
| ship_from_id       | integer             | null: false                   |
| days_delivery_id   | integer             | null: false                   |
| price              | integer             | null: false                   |
| user_id            | integer             | null:false, foreign_key: true |

### Association
- belongs_to :user
- has_many: purchase_history

##  buyer テーブル

| Column             | Type                | Options                       |
|--------------------|---------------------|-------------------------------|
| postal_code        | integer             | null: false                   |
| prefecture         | integer             | null: false                   |
| municipality       | string              | null: false                   |
| address            | string              | null: false                   |
| building_name      | string              |                               |
| phone_number       | string              | null: false                   |

### Association
- belongs_to :user
- has_many: purchase_history

##   purchase_historyテーブル

| Column             | Type                | Options                       |
|--------------------|---------------------|-------------------------------|
| buyer_id           | integer             | null:false, foreign_key: true |
| items_id           | integer             | null:false, foreign_key: true |


### Association
- belongs_to :items
- belongs_to :buyer