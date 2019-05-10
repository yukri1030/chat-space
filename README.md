# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## userテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|name|varchar(8)|null: false|
|e-mail|varchar(30)|null: false|
|group_id|integer|null: false, foreign_key: true|

### Asosiation
- belongs_to: group
- has_many :comments




## groupテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null:false, foreign_key: true|
|name|varchar(8)|null: false|
|user_id|integer|null: false, foreign_key: true|



### Asociation
- belongs_to :member, through:user
- has_many :chats, through: comments
- has_many :comments, through chat

## memberテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null:false, foreign_key: true|
|user_id|null: false, foreign_key :true|
|user_name|null: false, foreign_key: true|




### Asosication

- belongs_to :group
- has_many :users



## chatテーブル

|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true|
|------|----|---------|
|chat|text|
|img|MEDIUMBLOB｜
|comments|body|
|user_id|integer|null:false, foreign_key: true|

### Asociation
- belongs_to :user
- has_many :comments
- has_through :group



## commentsテーブル


|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true|
|------|----|---------|
|chat_id|integer|null:false, foreign_key: true|
|user_id|intefer｜null:false, foregin_key :true|
|group_id|interger|null:false, foreign_key: true|
|body|text|
|comments|body|
|img|MEDIUMBLOB|



### Asociation
- belongs_to :user, through group
- belongs_to :chat, through user



