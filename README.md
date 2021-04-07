## usersテーブル

Column | Type | Options
-|-|-
email | string | NOT NULL
password | string | NOT NULL
name | string | NOT NULL
profile | string | NOT NULL
occupation | string | NOT NULL
position | string | NOT NULL

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

Column | Type | Options
-|-|-
title | string | NOT NULL
catch_copy | text | NOT NULL
concept | text | NOT NULL
user | references | foreign_key: true

### Association
- belongs_to :user
- has_many :comments

## commentsテーブル

Column | Type | Options
-|-|-
text | text | NOT NULL
user | references | foreign_key: true
prototype | references | foreign_key: true

### Association
- belongs_to :user
- belongs_to :prototype