# SQL-vulnerable-web-app
this is vulnerable web app for sql injection attack and prevention for code.


##commands
test' OR 1=1#
test'; drop table accounts;

#database
USE `pythonlogin`;
CREATE TABLE IF NOT EXISTS `accounts` (
	`id` int(11) NOT NULL AUTO_INCREMENT,
  	`username` varchar(50) NOT NULL,
  	`password` varchar(255) NOT NULL,
  	`email` varchar(100) NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8; 

#fix
 # NEVER DO LIKE THIS
   result = cur.execute("SELECT * FROM users WHERE user = '%s'" % username)
 # DO LIKE THIS INSTEAD
   result = cur.execute("SELECT * FROM users WHERE user = %s", (username))
