# DB 設計

## users テーブル

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nickname           | string              | null: false             |
| email              | string              | null: false             |
| user_password      | string              | null: false             |
| family_name        | string              | null: false             |
| first_name         | string              | null: false             |
| family_name_kana   | string              | null: false             |
| birth_day          | date                | null: false             |

### Association
- has_many: items
- belongs_to :buyer
- has_one: credit_card


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

##  buyer テーブル

| Column             | Type                | Options                       |
|--------------------|---------------------|-------------------------------|
| postal_code        | integer             | null: false                   |
| prefecture         | date                | null: false                   |
| municipality       | integer             | null: false                   |
| address            | integer             | null: false                   |
| building_name      | string              | null: false                   |
| phone_number       | integer             | null: false                   |
| user_id            | integer             | null:false, foreign_key: true |

### Association
- belongs_to :user


##   credit_cardテーブル

| Column             | Type                | Options                       |
|--------------------|---------------------|-------------------------------|
| card_number        | integer             | null: false                   |
| card_year          | integer             | null: false                   |
| card_month         | integer             | null: false                   |
| security_code      | integer             | null: false                   |
| user_id            | integer             | null:false, foreign_key: true |

### Association
- belongs_to :user
