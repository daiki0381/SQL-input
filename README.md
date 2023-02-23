# SQLの基本

- 鬼滅テーブル(kimetsu)の名前カラム(name)と特徴カラム(feature)を取得

```
SELECT name, feature FROM kimetsu;
SELECT name AS '名前', feature AS '特徴' FROM kimetsu; // カラム名の変更
```

- 鬼滅テーブル(kimetsu)の全カラムを取得

```
SELECT * FROM kimetsu;
```

- 鬼滅テーブル(kimetsu)の呼吸カラム(kokyu)を取得 (重複なし)

```
SELECT DISTINCT(kokyu) FROM kimetsu;
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)が5より大きいレコードの名前カラム(name)と可愛いカラム(kawaii)を取得

```
SELECT name, kawaii FROM eva WHERE kawaii > 5;
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)が5より大きいand役割カラム(role)がパイロットのレコードを取得

```
SELECT * FROM eva WHERE kawaii > 5 AND role = 'パイロット';
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)が5より大きいor役職カラム(role)がパイロットのレコードを取得

```
SELECT * FROM eva WHERE kawaii > 5 OR role = 'パイロット';
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)が4〜6のレコードを取得

```
SELECT * FROM eva WHERE kawaii BETWEEN 4 AND 6;
```

- エヴァテーブル(eva)の役職カラム(role)がパイロットか作戦部長のレコードを取得

```
SELECT * FROM eva WHERE role = 'パイロット' OR role = '作戦部長';
SELECT * FROM eva WHERE role IN ('パイロット', '作戦部長');
```

- エヴァテーブル(eva)の名前カラム(name)が「ア」から始まるレコードを取得

```
SELECT * FROM eva WHERE name LIKE 'ア%';
```

- エヴァテーブル(eva)の役職カラム(role)がNULLのレコードを取得

```
SELECT * FROM eva WHERE role IS NULL;
```

- エヴァテーブル(eva)のレコードを2行のみ取得

```
SELECT * FROM eva LIMIT 2;
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)の昇順で取得

```
SELECT * FROM eva ORDER BY kawaii;
```

- エヴァテーブル(eva)の可愛いカラム(kawaii)の降順で取得

```
SELECT * FROM eva ORDER BY kawaii DESC;
```

# GROUP BY

- メンバー会員テーブル(members)の2021-02-13の会員登録数を取得

```
SELECT COUNT(name) FROM members WHERE created_day = '2021-02-13';
```

- メンバー会員テーブル(members)の日毎の会員登録数を取得

```
SELECT created_day, COUNT(name) FROM members GROUP BY created_day; // created_dayの同じ値をまとめる
```

- メンバー会員テーブル(members)の日毎のチャネル(ad, web)ごとの会員登録数を取得

```
SELECT created_day, channel, COUNT(name) FROM members GROUP BY created_day, channel;
```

- メンバー会員テーブル(members)の日毎の会員登録数と平均年齢と最大年齢を取得

```
SELECT created_day, COUNT(name), AVG(age), MAX(age) FROM members GROUP BY created_day;
```
