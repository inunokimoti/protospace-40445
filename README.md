# ProtoSpaceのER図


| ## usersテーブル                              |
|                                               |
| email（string型, NOT NULL, ユニーク制約）      |
| encrypted_password（string型, NOT NULL）      |
| name（string型, NOT NULL）                    |
| profile（text型, NOT NULL）                   |
| occupation（text型, NOT NULL）                |
| position（text型, NOT NULL）                  |


### Association

- has_many :prototypes
- has_many :comments

| ## prototypesテーブル                         |
|                                              |
| title（string型, NOT NULL）                   |
| cath_copy（text型, NOT NULL）                 |
| concept（text型, NOT NULL）                   |
| user（references型, NOT NULL, 外部キー）      |


### Association

- has_many :comments
- belongs_to :user


| ## commentsテーブル                           |
|                                              |
| content（text型, NOT NULL）                   |
| prototype（references型, NOT NULL, 外部キー） |
| user（references型, NOT NULL, 外部キー）      |


### Association

- belongs_to :prototype
- belongs_to :user