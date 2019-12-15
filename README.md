# README
## chat-space db設計

### users テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,index: true|
|address|string|null: false|
|paddword|string|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :groups
- belongs_to :groups_users
- has_many ：chats

### chate テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|string|null: false,index: true|
|group_id|string|null: false,index: true|
|text|integer|index: true|
|image|integer|index: true|

### Association
- belongs_to: user
- belongs_to :group
- has_many :text


## chate groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user