# 2021gsc_IbukiShibayama
2021年度古橋ゼミ論用レポジトリ
# PLATEAUの整備フローを基にした相模原キャンパスの建物3Dオープンデータの制作
2021年度 ゼミ論文

青山学院大学 地球社会共生学部 地球社会共生学科

柴山息吹/IBUKI SHIBAYAMA

学生番号 1A119084

指導教員 古橋大地 教授

© Furuhashi Laboratory/Ibuki Shibayama, CC BY 4.0

## Abstract
本研究では、国土交通省が進める3D都市モデルのオープンデータプラットフォーム「PLATEAU」の整備フローを参考に、相模原キャンパスのモデリングを行った。LOD2以上の詳細なモデルができていない地域で、市民がデータ整備に貢献できるようなフローを検証し、そこで生まれた課題をまとめた。
## Introduction
日本全国の3D都市モデルデータを整備し、オープンデータとして流通させる「Project PLATEAU」は国土交通省の主導で2020年度から開始された。PLATEAUのデータ整備は規模が大きくてもコストを低減させることが可能で、2021年8月に整備対象の56都市分の3D都市モデルのオープン化が完了した（国土交通省, 2021）。しかし各地域のデータにおいて、LOD1と呼ばれる、建物と高さの情報（PLATEAU Learning）のみが登録されているものが多く、さらに詳細なLOD2以上のデータ整備が課題だといえる。そこで今回は、PLATEAUの整備フローを参考に、市民が参加できるような3D都市データの整備方法を検証し、成果物をオープンデータ化する。

* 資料1:LODについて（出典：PLATEAU Learning, [https://www.mlit.go.jp/plateau/learning/](https://www.mlit.go.jp/plateau/learning/)）
<img width="70%" alt="2022-01-31 (2)" src="https://user-images.githubusercontent.com/72287333/151738911-ae91e841-239d-4983-8792-9f0b5b51b863.png">

## Methods
PLATEAUの整備フローは、2次元の地図情報（都市計画基本図）に3次元の航空測量情報を組み合わせ、さらに建物のメタデータ（都市計画基礎調査情報）を付与させるというものであり（空間情報クラブ, 2021）、全てオープンデータから成り立っている。この流れを基に、市民が参加できるように考案した全体の整備フローを以下の図1で示す。ただし、ここでの市民とは、ネットがある環境でパソコンを使ったファイルの操作や編集ができる者、と定義する。なお本研究では、国土交通省が示すデータの作成方法のうち「現地調査や測量などにより、新規に取得する」（国土交通省都市局, 2021）を選択し、実践する範囲は建物の高さや形状を反映した幾何オブジェクトの作成までとする。
* （図1）
<img width="70%" alt="2022-01-31" src="https://user-images.githubusercontent.com/72287333/151733088-739413d1-c88d-453f-9ebe-3cf8f73855cf.png">

* 資料2:国土交通省が示す標準的な作業手順（出典：3D都市モデル標準作業手順書, [https://www.mlit.go.jp/plateau/file/libraries/doc/plateau_doc_0002_ver01.pdf](https://www.mlit.go.jp/plateau/file/libraries/doc/plateau_doc_0002_ver01.pdf)）
<img width="40%" alt="2022-02-05" src="https://user-images.githubusercontent.com/72287333/152623098-70e122ef-bf9a-4bf3-9cdc-e9c82071ec17.png">

PLATEAUにおける3種類のリソースに対し、それぞれにデータを割り振った。2次元の地図情報にはOpenStreetMapや国土地理院地図を、3次元の情報にはDronebirdをはじめとする民間団体によるドローンの測量データを、メタデータにはLiDAR機能を搭載したスマートフォンや360°カメラによる3Dスキャンのデータを対応させた。ドローンの測量と3Dスキャンのデータについては、各々が取得した後にオープンデータとして公開することを前提とする。
本研究では、青山学院大学相模原キャンパスを対象に、この2つのデータの取得から3Dモデルの作成してオープンデータとして公開する工程（図3）を実践し、市民によるデータ整備の可能性を検証する。
* （図3）
<img width="70%" alt="2022-01-31 (1)" src="https://user-images.githubusercontent.com/72287333/151733346-2bd3162b-4d20-40f3-b826-7fb43e80254c.png">

ドローンの測量は、古橋大地教授の主導の下2021年12月15日にエアロセンス社製エアロボウイングを用いて行った。そこで得られたLASデータをCoudCompareでサイズ調整とトリミングを行ってPLYファイルにエクスポートし、Blenderで点群に沿うようにメッシュの3Dモデルを作成する。このモデルをOBJやFBXなどのファイルにエクスポートし、GitHubやSketchfabなどでオープンデータとして公開する。なお、CloudCompareとBlenderを選択したのは、無料ソフトウェアであり、より多くのユーザーが最低限のコストで利用できると考えたからである。オープンデータとしてOpenStreetMapのような検証や修正の可能性を持つことを踏まえ、3次元CADのような製図方式でなくとも妥当だと判断した。
## Results
まず、ドローンを用いた測量からはキャンパス全体の高精度な点群データが得られ、ガラス面の反射による崩れも少なく、3Dモデリングには支障が無いことが確認できた。点群データは古橋教授によって間引きされ、58.2GBから3.4GBまでの5段階のサイズのLASファイルでGoogle Driveで共有された。それらを比較し、1.84GBのものがモデリングに必要な最低限の点群を有していると判断できたため、このデータを利用することにした。
このLASファイルをCloudCompareにインポートし、Segment機能でキャンパスの各棟ごとにトリミングした後、それぞれをPLYファイルとしてエクスポートした。

<img width="70%" alt="2022-01-31 (3)" src="https://user-images.githubusercontent.com/72287333/151740664-6113297f-1517-41e0-a276-03f2cfd1cdca.png">
<img width="70%" alt="2022-01-31 (4)" src="https://user-images.githubusercontent.com/72287333/151740673-062cb2da-5e51-46cf-92b8-5ad977cee361.png">

Blenderでのモデリングは、相模原キャンパスのランドマーク的存在であるC棟ウェスレーチャペルを優先して行った。PLYファイルをBlenderにインポートしたら、原点を3Dカーソルに合わせ、点群に沿うようにキューブのオブジェクトを編集していった。操作は基本的なものに制限し、主にオブジェクトの移動、回転、サイズ変更、ループカット（辺の追加）、面の押し出し、面の作成のみでモデリングを行った。

<img width="70%" alt="2022-01-31 (5)" src="https://user-images.githubusercontent.com/72287333/151741123-4abf08bc-1928-49b2-ba88-84d36bab24d6.png">
<img width="70%" alt="2022-01-31 (6)" src="https://user-images.githubusercontent.com/72287333/151741131-457d7951-150a-40fc-ac0f-9b0daa1ed745.png">

結果、C棟のLOD3相当のモデルが完成し、OBJ形式でエクスポートし、GitHubとSketchfabでオープンデータ（CC-BY-4.0）として公開した。

<img width="70%" alt="2022-01-31 (7)" src="https://user-images.githubusercontent.com/72287333/151741247-a38555ff-51b2-4817-8714-e276b9a5e3fc.png">

* [動画資料](https://youtu.be/N7c88h7HLcg)
* [Sketchfab](https://sketchfab.com/3d-models/wesley-chapel-agu-sagamihara-campus-lod3-e85177e3f4ed4f66a96d55f007abebe7)

また、スマートフォンやタブレットでの3Dモデルの共有方法として、GlitchでA-frameをコーディングしてマーカーベースARを作成した。

<img width="70%" alt="2022-01-31 (9)" src="https://user-images.githubusercontent.com/72287333/151753286-c36ae42e-d285-4843-91ba-4ef62b020119.png">

* [ソースコード](https://glitch.com/edit/#!/solid-amplified-piranha)
* ARマーカー
  * QRコードをスマートフォンやタブレットで撮影し、リンク先でもそのままカメラを向け続けると3Dチャペルが現れる。
  * マーカーに対して垂直に表示されるので、画面を上に向けた状態で見ることを推奨する。

![armarker_sc_c_l](https://user-images.githubusercontent.com/72287333/151741820-760f2e30-9fe2-403e-ba31-4dc10707fe71.png)

* [動画資料](https://youtu.be/6uI9PRdn81g)

## Discussion
今回実践した各工程において発見した課題は以下の通りである。
#### データの取得
ドローンによる点群データの取得は非常に高精度であったが、エアロボウイングよりもスペックが低い場合、モデリングが可能な最低限のデータが得られるかどうかが疑問である。多様な民間団体や市民が整備フローに参加するためには、ドローンのスペックと点群データの精度の相関関係を検証する必要があると感じた。
また、屋内の3DスキャンについてはC棟のLOD2のモデリングが完成してから行う予定であったが、時間を割くことができず、最終発表までの実施は断念した。
#### データの調整
CloudCompareにおけるLASファイルのインポート、トリミング、PLYファイルへのエクスポートの一連の作業において致命的な問題は無かった。しかし、サイズの大きいファイルのエクスポートの際に発生するエラーには注意が必要である。アラートのウィンドウがバグでクローズできず、アプリを閉じるかPCを再起動するしかないため、一度エラーに引っかかると編集内容が保存できなくなる。保存ボタンを押すとフォーマットをバイナリかASCIIか選択するウィンドウが表示されるが、ASCIIの方がエラーが出にくい。

<img width="70%" alt="2022-01-31 (10)" src="https://user-images.githubusercontent.com/72287333/151774461-a4667a47-7f03-48ee-b362-8018f51d6ff6.png">

#### モデリング
Blenderでのモデリングにおいても特に致命的な問題は無かったが、ループカットや押し出しを積み重ねるうちに構造が複雑化して引き起こされる問題があった。例えば、細かい調整や修正を行おうとすると頂点や辺が二重に出来てしまうことや（図4）、面の裏表が逆向きになってしまう（図5）ことがある。こういった問題がないかこまめにチェックし、重複があればマージし、面が逆向きであれば正しい向きへ反転させる必要がある。このような手間があり、作成は想定していたよりも多くの時間を要した。結果として屋内の3Dスキャンや他の棟のモデリングが実施できなかったため、早期から計画的に作業を進め、場合によっては他の人にも助けを依頼するべきだった。
* 図4 ※赤色の矢印が指す頂点と辺がそれぞれ重複している。
<img width="70%" alt="2022-01-31 (11)" src="https://user-images.githubusercontent.com/72287333/151774553-c09c8d07-d5c6-44c4-a688-fc06a4a9a7cb.png">

* 図5 ※黄色の矢印が指す面は裏向きに、黄緑色の矢印が指す部分は裏向きと表向きの面が重複している。
<img width="70%" alt="2022-01-31 (12)" src="https://user-images.githubusercontent.com/72287333/151774853-181b5d83-c46a-4235-847e-4035e81dc004.png">

また、点群データには厚みが存在していることによる誤差について言及する。Blenderのメジャー機能を利用し、C棟の屋根の点群を水平方向から測定したところ、9~12cmほどの厚みが確認できた（図6）。モデリングの際には全体のバランスを見ながらオブジェクトの面が点群に接触するように作業したため、点群の厚み以下の誤差の発生が想定できる。しかし、誤差が大きくても10数cmであることや、オープンデータとして検証や修正を通して精度を上げていくという前提から、
* 図6
<img width="792" alt="2022-02-05 (1)" src="https://user-images.githubusercontent.com/72287333/152625796-65f31697-e6f9-4d74-84b6-6c6cc2743e79.png">

今回は基本的に全機能が無料で使えるという理由でBlenderを採用したが、直感的に操作することが難しいため苦戦するケースも多いと感じた。Blender未経験者に対してモデリングの実践とそのフィードバックを依頼し、市民が参加する整備フローに適するかどうか、ペルソナの基準を変更するかどうか検証する必要がある。
## Conclusion
本研究は市民参加型の3D都市モデルの整備フローを考案し、まずは自ら実践するというスタンスで臨んだが、今後は他の手法やツールとの比較、他者による試験的な実践が必要だと感じた。また、データを作るだけでなく、オープンデータとして公開し、どのように応用していくかについても構想を練りたい。特に、VR東大やバーチャル渋谷のような仮想空間の共有や、キャンパスのモデルを利用したハッカソンの開催などを計画していく予定である。
## References
[https://docs.google.com/spreadsheets/d/1bJ8EX_SESjuZiktEz_Et8UpGBwUkUeSjRpzbrs9SqyI/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1bJ8EX_SESjuZiktEz_Et8UpGBwUkUeSjRpzbrs9SqyI/edit?usp=sharing)
## Acknowledgements
本研究を進めるにあたり、青山学院大学 地球社会共生学部 古橋大地教授にフィールドワークの機会や貴重な助言を賜りました。深く感謝致します。
#### グラレコ
<img width="70%" alt="無題25_20220131205215 jpg" src="https://user-images.githubusercontent.com/72287333/151811449-c73c8b4d-4190-4f61-a418-6957a8320de3.png">

#### Medium
[https://medium.com/furuhashilab/%E3%81%95%E3%81%8C%E3%81%8D%E3%82%83%E3%82%933d%E3%83%A2%E3%83%87%E3%83%AB-%E3%82%BC%E3%83%9F%E8%AB%96-fd3b3355cb10](https://medium.com/furuhashilab/%E3%81%95%E3%81%8C%E3%81%8D%E3%82%83%E3%82%933d%E3%83%A2%E3%83%87%E3%83%AB-%E3%82%BC%E3%83%9F%E8%AB%96-fd3b3355cb10)
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
