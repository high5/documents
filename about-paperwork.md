
************************
DATABASE
************************

+---------------------+
| Tables_in_paperwork |
+---------------------+
| attachment_version  |
| attachments         |
| language_user       |
| languages           |
| migrations          |
| note_user           |
| notebook_user       |
| notebooks           |
| notes               |
| password_reminders  |
| settings            |
| shortcuts           |
| tag_note            |
| tag_user            |
| tags                |
| users               |
| versions            |
+---------------------+

users
+----------------+---------------------+------+-----+---------------------+----------------+
| Field          | Type                | Null | Key | Default             | Extra          |
+----------------+---------------------+------+-----+---------------------+----------------+
| id             | bigint(20) unsigned | NO   | PRI | NULL                | auto_increment |
| username       | varchar(255)        | NO   | UNI | NULL                |                |
| password       | varchar(255)        | NO   |     | NULL                |                |
| firstname      | varchar(255)        | NO   |     | NULL                |                |
| lastname       | varchar(255)        | NO   |     | NULL                |                |
| is_admin       | tinyint(3) unsigned | NO   |     | 0                   |                |
| remember_token | varchar(100)        | YES  |     | NULL                |                |
| created_at     | timestamp           | NO   |     | 0000-00-00 00:00:00 |                |
| updated_at     | timestamp           | NO   |     | 0000-00-00 00:00:00 |                |
| deleted_at     | timestamp           | YES  |     | NULL                |                |
+----------------+---------------------+------+-----+---------------------+----------------+

versions
+-----------------+---------------------+------+-----+---------------------+----------------+
| Field           | Type                | Null | Key | Default             | Extra          |
+-----------------+---------------------+------+-----+---------------------+----------------+
| id              | bigint(20) unsigned | NO   | PRI | NULL                | auto_increment |
| previous_id     | bigint(20) unsigned | YES  | MUL | NULL                |                |
| next_id         | bigint(20) unsigned | YES  | MUL | NULL                |                |
| title           | varchar(255)        | NO   |     | NULL                |                |
| content_preview | varchar(255)        | NO   |     | NULL                |                |
| content         | text                | NO   |     | NULL                |                |
| created_at      | timestamp           | NO   |     | 0000-00-00 00:00:00 |                |
| updated_at      | timestamp           | NO   |     | 0000-00-00 00:00:00 |                |
| deleted_at      | timestamp           | YES  |     | NULL                |                |
+-----------------+---------------------+------+-----+---------------------+----------------+
