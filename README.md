# README
## chat-space db設計

### users テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|address|string|null: false, foreign_key: true|
|paddword|string|null: false, foreign_key: true|

### Association
- has_many :text
- has_many :messege

### chate テーブル
|Column|Type|Options|
|------|----|-------|
|text|integer|null: false, foreign_key: true|
|messege|integer|null: false, foreign_key: true|
|image|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :text
- belongs_to: user
- has_many :messege

## chate groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user