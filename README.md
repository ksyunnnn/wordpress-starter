## Get started

```
git clone [this repo]
cd [dir]
vagrant up
```

```
mysql -u root
CREATE DATABASE mywordpress;
GRANT ALL PRIVILEGES ON mywordpress.* TO myuser@localhost IDENTIFIED BY 'mypass' WITH GRANT OPTION;

# マイグレーションが必要な場合
mysql -u [user] -p[password] [database name] < hoge.sql >out.txt
# ※-pの後にスペース入らないことに注意
```

access http://localhost:8080

## 参考

https://utano.jp/entry/2014/11/vagrant_guest_additions_update_error/
