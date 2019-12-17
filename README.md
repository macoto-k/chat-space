# README
## chat-space db設計

### users テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,index: true|
|address|string|null: false|
|paddword|string|null: false|

### Association
- has_many :groups,through: groups_users
- has_many :groups_users
- has_many ：chats

### groups テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|nnull: false, unique: true|

### Association
- has_many :groups_users
- has_many :users, through: groups_users
- has_many :chats

### chats テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false,trueforeign_key: true|
|group|references|null: false,foreign_key: true|
|text|integer||
|image|integer||

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user