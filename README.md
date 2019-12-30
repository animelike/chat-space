## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|

### Association
- has_many :group, through: :groups_users
- has_many :message

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|comment|text|null: false|
|image|string|

### Association
- belongs_to :user
- belomgs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group|string|null: false|
|member|string|null: false|

### Association
- has_many :user, through: :groups_users
- has_many :message

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
