# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false|
|mail|string|null: false, unipue: true|

### Association
- has_many :practices,through: members
- has_many :messages
- has_many :members
- has_many :gyms
- has_many :templates

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false,unique:true|

### Association
- has_many :practices


## practicesテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|place|string|
|daytime|string|
|body|text|
|group_id|integer|null: false,foreign_key:true|
|gym_id|integer|null: false,foreign_key:true|
|template_id|integer|null: false,foreign_key:true|

### Association
- has_many :users,through: members
- has_many :gyms
- has_many :templates
- belongs_to :group

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|practice_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :practice

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|practice_id|integer|null:false,foreign_key:true|
|user_id|integer|null:false,foreign_key:true|

### Association
- belongs_to :practice
- belongs_to :user

## gymsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|address|string|
|user_id|integer|null:false,foreign_key:true|
|gym_time_id|integer|null:false,foreign_key:true|

### Association
- has_many :gym_times
- belongs_to :user
- belongs_to :practice

## gym_timesテーブル

|Column|Type|Options|
|------|----|-------|
|start_time|time|null:false|
|exit_time|time|

### Association
- belongs_to :gym

## templatesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null,false|
|image|string|
|user_id|null: false,foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user
- belongs_to :practice