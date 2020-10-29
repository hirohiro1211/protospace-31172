#テーブル設計

##user テーブル
|Colum      |Type   |Options      |
|-----------|-------|-------------|
|email      |string |NOT NULL     |
|password   |string |NOT NULL     |
|name       |string |NOT NULL     |
|profile    |text   |NOT NULL     |
|occupation |text   |NOT NULL     |
|position   |text   |NOT NULL     |

### Association
-has_many :prototypes
-has_many :comments


##prototypes テーブル
|Colum      |Type     |Options      |
|-----------|---------|-------------|
|title      |string   |NOT NULL     |
|catch_copy |text     |NOT NULL     |
|concept    |text     |NOT NULL     |
|image      |ActiveStorageで実装     |
|user       |reference|             |

### Association
-belongs_to :user
-has_many :comments


##comments テーブル
|Colum      |Type     |Options      |
|-----------|---------|-------------|
|text       |text     |NOT NULL     |
|user       |reference|             |
|prototype  |reference|             |

### Association
-belongs_to :user
-belongs_to :prototype