# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false|
|mail|string|null: false, unipue: true|

### Association
- 
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false,unique:true|

- belongs_to :group
- belongs_to :user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null:false,foreign_key:true|
|user_id|integer|null:false,foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user

## gymsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|day|string|
|time|string|
|address|string|
|user_id|integer|null:false,foreign_key:true|



### Association
- belongs_to :group
- belongs_to :user

## friendsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false,foreign_key:true|
||


### Association
- belongs_to :group
- belongs_to :user

## practicesテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|place|string|
|daytime|string|
|body|text|
|group_id|integer|null: false,foreign_key:true|


### Association
- belongs_to :group
- belongs_to :user

## templates モデル
|body|text|null,false|
|image|string|
|user_id|null: false,foreign_key:true|