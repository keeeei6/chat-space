## usresテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index|
|email|string|null: false, unique: true|
|password|string|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_usres

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|content|text|
|image|string|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|

### Association
- has_many :users, through: :users
- has_many :messages
- has_many :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|references|null: false, foreign_key: true|
|user_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
