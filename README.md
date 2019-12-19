# README

##group_usersテーブル

|Colunm|Type|Options|
|------|----|-------|
|user|references|null:false,foreign_key: true|
|group|references|null:false,foreign_key: true|

## Association
- belongs_to: group
- belongs_to: user


##usersテーブル
|Colunm|Type|Options|
|------|----|-------|
|name|string|null:false|
|email|string|null:false|
|password|string|null:false|

## Association
- has_many: groups,through: :groups_users
- has_many: messages
- has_many: group_users



##groupsテーブル
|Colunm|Type|Options|
|------|----|-------|
|groupname|string|null:false|

## Association
- has_many: users,through: :groups_users
- has_many: messages
- has_many: group_users



##messagesテーブル
|Colunm|Type|Options|
|------|----|-------|
|text|text||
|image|string||
|group|references|null:false,foreign_key: true|
|user|references|null:false,foreign_key: true|


## Association
- belongs_to: user
- belongs_to: message