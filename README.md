# テーブル設計

## users テーブル

| Column          | Type    | Options     |
| --------------- | ------- | ----------- |
| nickname        | string  | null: false |
| email           | string  | null: false |
| password        | string  | null: false |
| last_name       | string  | null: false |
| first_name      | string  | null: false |
| last_name_kana  | string  | null: false |
| first_name_kana | string  | null: false |
| user_birth_date | integer | null: false |

### Association

- has_many :items
- has_many :purchase_records

## itemsテーブル

| Column                   | Type       | Options                      |
| ------------------------ | ---------- | ---------------------------- |
| item_image               |            |                              |
| item_name                | string     | null: false                  |
| item_info                | text       | null: false                  |
| item_category            | string     | null: false                  |
| item_sales_status        | string     | null: false                  |
| item_shipping_fee_status | string     | null: false                  |
| item_prefecture          | string     | null: false                  |
| item_scheduled-delivery  | string     | null: false                  |
| item_price               | integer    | null: false                  |
| user                     | references | null: false foreign_key: true|

### Association

- belongs_to :user
- has_one :purchase_records

## purchase_records テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| user      | references | null: false   foreign_key: true|
| item      | references | null: false   foreign_key: true|

### Association

- belongs_to :user
- has_one :item
- has_one :addresse

## addressesテーブル

| Column       | Type       | Options       |
| ------------ | ---------- | ------------- |
| postal_code  | string     | null: false   |
| prefecture   | string     | null: false   |
| city         | string     | null: false   |
| addresses    | string     | null: false   |
| building     | string     |               |
| phone-number | string     | null: false   |

### Association

- has_one :purchase_records


