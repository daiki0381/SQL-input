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
