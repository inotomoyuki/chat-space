# Pictweet DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, index:true|
|password|string|null: false, index:true|
|group|string|null: fallse|
### Association
- has_many :tweets
- has_many :comments
- belongs_to :groups

## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :tweet
- belongs_to :user