# テーブル設計

## users テーブル

| Column      | Type   | Options                  |
| ----------- | ------ | ------------------------ |
| nickname    | string | null: false, unique:true |
| email       | string | null: false, unique:true |
| password    | string | null: false              |
| birthday    | date   | null: false              |

### Association

- has_many :thermometers

## thermometers テーブル

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| body_temperature| integer    | null: false                    |
| date            | date       | null: false                    |
| condition_id    | integer    | null: false                    |
| memo            | text       | null: false                    |
| user            | references | null: false, foreign_key: true |

### Association

- belongs_to :user