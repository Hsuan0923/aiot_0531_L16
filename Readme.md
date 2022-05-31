# AIoT Github

## Lecture 16: IoT Flask Web (deploy to heroku)
### 目標：把flask highcharts 推播到heroku public
### step 0：
* 下載HeidiASQL, VS code
* 註冊Heroku, github
### step 1 : Clone this github
* git clone https://github.com/huanchen1107/aiot0530-start-no-token 到 local\aiot0531 folder
* 把local的 \aiot0531.git 殺掉 (產生自己的git管理員) 方便建立新的git repository
* 推送至github 建立新的 aiot0531 https://github.com/Hsuan0923/aiot_0531_L16
### step 2 : install some package


```python
pip install gunicorn Flask==2.0.1 Jinja2==3.0.1 psycopg2 sklearn pandas numpy
```

### step 3: add an heroku postgredb

* register heroku account
* go to dashboard
* new an app
* go to resource and add-on an Heroku postgredb

### step 4: login to heroku pstgredb using HeidiSQL

* 進去Heroku postgredb進行調整
* 點擊Settings -> View Credentials
* 查看各項資訊(Host,User,Password...等)
* 打開HeidiSQL 將相對應的資訊填入 (app.py也要填入)
* 網路類型：PostgreSQL(TCP/IP) Library：libpq-12.dll

```sql
myserver ="<fill-in-Heroku-Postgredb-DB-sever>"
myuser="<fill-in-Heroku-Postgredb-DB-user>"
mypassword="<fill-in-Heroku-Postgredb-DB-pwd>"
mydb="<fill-in-Heroku-Postgredb-DB-db>"

```
### step 5: import postgredb (in db/postgre.db)

* 連接成功後 匯入postgres.sql

### step 6: setting db in app.py

* 修改app.py裡的以下程式碼 將剛才的資訊填入相對應的內容

```sql
myserver ="<fill-in-Heroku-Postgredb-DB-sever>"
myuser="<fill-in-Heroku-Postgredb-DB-user>"
mypassword="<fill-in-Heroku-Postgredb-DB-pwd>"
mydb="<fill-in-Heroku-Postgredb-DB-db>"

```
### step 7: testing locally by running python app.py

* 在終端機執行python app.py
* 查看local端是否能跑出highchart並正常運行

### step 8: deploy to github (new public github repositoy)

delete .git and git remote add origin master github.com/xxxxx

### step 9: Heroku deploy from github

* 點擊剛剛在Heroko建立好的app->deploy->connect github->aiot_0531_L16
* enable後還要再deploy branch (可以去Logs看他deploy的狀態)

### step 10: Complete

* Build Succeeded後就可以去Open app 成功！
* 我的Link：https://aiot0531hj.herokuapp.com/

### Success image

* 點擊SetRandom後出現的highcahrt
![](static%5Crandom.jpg)






