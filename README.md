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
## usersテーブル
|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true|
|------|----|---------|
|name|string|nill:false, foreign_key: true|
|e-mail|varchar(30)|null:false|
|group_id|null:false, foreign_key: true|
|message_id|null:false, foreign_key: true|

### Asociation
- belongs_to :group
- has_many :messages


## groupテーブル

|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true｜
|name|string|null: false|
|member_id|integer|null:false, foreign_key: true|

### Adociation
- has_many: members 

## memberテーブル

|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true｜
|name|string|null: false|
|group_id|integer|null:false, foreign_key: true｜

- belongs_to: group


## messageテーブル

|Column|Type|Opitions|
|------|----|---------|
|id|integer|null:false, foreign_key: true｜
|massage|text|
|img|string|

### Association

- belongs_to: user
