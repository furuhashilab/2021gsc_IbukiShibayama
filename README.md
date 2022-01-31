# 2021gsc_IbukiShibayama
2021年度古橋ゼミ論用レポジトリ
# PLATEAUの整備フローを基にした相模原キャンパスの建物3Dオープンデータの制作
2021年度 ゼミ論文

青山学院大学 地球社会共生学部 地球社会共生学科

柴山息吹/IBUKI SHIBAYAMA

学生番号 1A119084

指導教員 古橋大地 教授

© Furuhashi Laboratory/Ibuki Shibayama, CC BY 4.0

## 概要
本研究では、国土交通省が進める3D都市モデルのオープンデータプラットフォーム「PLATEAU」の整備フローを参考に、相模原キャンパスのモデリングを行った。LOD2以上の詳細なモデルができていない地域で、市民がデータ整備に貢献できるようなフローを検証し、そこで生まれた課題をまとめた。
## Introduction
日本全国の3D都市モデルデータを整備し、オープンデータとして流通させる「Project PLATEAU」は国土交通省の主導で2020年度から開始された。PLATEAUのデータ整備は規模が大きくてもコストを低減させることが可能で、2021年8月に整備対象の56都市分の3D都市モデルのオープン化が完了した（国土交通省, 2021）。しかし各地域のデータにおいて、LOD1と呼ばれる、建物と高さの情報（PLATEAU Learning）のみが登録されているものが多く、さらに詳細なLOD2以上のデータ整備が課題だといえる。そこで今回は、PLATEAUの整備フローを参考に、市民が参加できるような3D都市データの整備方法を検証し、成果物をオープンデータ化する。

* 資料1:LODについて（出典：PLATEAU Learning, [https://www.mlit.go.jp/plateau/learning/](https://www.mlit.go.jp/plateau/learning/)）
<img width="70%" alt="2022-01-31 (2)" src="https://user-images.githubusercontent.com/72287333/151738911-ae91e841-239d-4983-8792-9f0b5b51b863.png">

## Methods
PLATEAUの整備フローは、2次元の地図情報（都市計画基本図）に3次元の航空測量情報を組み合わせ、さらに建物のメタデータ（都市計画基礎調査情報）を付与させるというものであり（空間情報クラブ, 2021）、全てオープンデータから成り立っている。この流れを基に、市民が参加できるように考案した全体の整備フローを以下の図1で示す。ただし、ここでの市民とは、ネットがある環境でパソコンを使ったファイルの操作や編集ができる者、と定義する。
* （図1）
<img width="70%" alt="2022-01-31" src="https://user-images.githubusercontent.com/72287333/151733088-739413d1-c88d-453f-9ebe-3cf8f73855cf.png">

PLATEAUにおける3種類のリソースに対し、それぞれにデータを割り振った。2次元の地図情報にはOpenStreetMapや国土地理院地図を、3次元の情報にはDronebirdをはじめとする民間団体によるドローンの測量データを、メタデータにはLiDAR機能を搭載したスマートフォンや360°カメラによる3Dスキャンのデータを対応させた。ドローンの測量と3Dスキャンのデータについては、各々が取得した後にオープンデータとして公開することを前提とする。
本研究では、青山学院大学相模原キャンパスを対象に、この2つのデータの取得から3Dモデルの作成してオープンデータとして公開する工程（図2）を実践し、市民によるデータ整備の可能性を検証する。
* （図2）
<img width="70%" alt="2022-01-31 (1)" src="https://user-images.githubusercontent.com/72287333/151733346-2bd3162b-4d20-40f3-b826-7fb43e80254c.png">

まず、ドローンの測量は古橋大地教授の主導の下、2021年12月15日にエアロセンス社製エアロボウイングを用いて行った。そこで得られたLASデータをCoudCompareでサイズ調整とトリミングを行ってPLYファイルにエクスポートし、Blenderで点群に沿うようにメッシュの3Dモデルを作成する。このモデルをOBJやFBXなどのファイルにエクスポートし、GitHubやSketchfabなどでオープンデータとして公開する。なお、CloudCompareとBlenderを選択したのは、無料ソフトウェアであり、より多くのユーザーが最低限のコストで利用できると考えたからである。

## Results
## Discussion
## Conclusion
## References
## Acknowledgements
#### Medium
#### スライド
[https://docs.google.com/presentation/d/19zjQCWRxxe3eguYAZYU1q5sLG8w0jMO8JjFAyZOWEBM/edit?usp=sharing](https://docs.google.com/presentation/d/19zjQCWRxxe3eguYAZYU1q5sLG8w0jMO8JjFAyZOWEBM/edit?usp=sharing)
#### 先行事例/既往研究
1. [PLATEAU](https://www.mlit.go.jp/plateau/?fbclid=IwAR2nENW2VCgIgpTdS7G2wIezhcJVmthRkynTP8YXiN8ybGT9Fkn_qOQpY6s)
2. [VR東大](https://vr.u-tokyo.ac.jp/virtualUT/)
3. [バーチャル渋谷](https://cluster.mu/w/79347fb9-05f5-429e-ab5f-8951ee8cd966)
#### 新規性
* 市民による3Dモデル整備の可能性を実践しながら検証する点。
* キャンパスの3Dモデルをオープンデータ化する点。
#### Advent Calendar
* [Medium](https://medium.com/furuhashilab/2021-12-13-advent-calendar-241ebedc0fa5)
#### Sketchfab
* [https://sketchfab.com/ibukilego](https://sketchfab.com/ibukilego)
## 参考文献リスト
https://docs.google.com/spreadsheets/d/1bJ8EX_SESjuZiktEz_Et8UpGBwUkUeSjRpzbrs9SqyI/edit?usp=sharing
