## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|email|string|null: false|
|pass|string|null: false|

## Association
- has_many :messeges
- has_many :groups_users 
- has_many :groups, through: :groups_users


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|user_id|integer|null: false|

## Association
- has_many :messeges
- has_many :users
- has_many :users, through: groups_users


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user
