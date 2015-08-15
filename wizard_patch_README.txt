Salome-Meca 2014.1用 Asterモジュール内ウィザード「弾性応力解析改」追加パッチ
by Takeru who belongs to JSWG -Japan Salome-Meca Working Group-

概要；
Salome-Meca 2014.1 Asterモジュールに「弾性応力解析改」ウィザードを追加します。
同時に、すでに搭載されている各ウィザードを多言語化し、日本語を提供します。

詳細：
Salome-Meca は、プリポストを提供するGUIツール「Salome」と
ソルバ部分を提供する「Code-Aster」で構成されています。

Code-Asterでは、commファイルと呼ばれるコマンドファイルにより
解析が実行されますが、これはテキストファイルで作成する必要があります。

Salome-Mecaでは、解析を実行する部分をAsterモジュールというGUIで提供されており、
その中にcommファイルを簡単に作成するためのウィザードがいくつか用意されています。

しかし、これらのウィザードは英語のみであり、日本語は用意されておりません。

また、すでに用意されている「linear-elastic」ウィザードは
弾性応力解析のためのウィザードですが、
与えられる境界条件は、変位拘束（強制変位含む）と面に対する圧力のみで、
点、エッジ、及び面に荷重を与えることができませんでした。

そこで、主なウィザードを多言語化し、日本語を提供した上で、
「linear-elastic」に荷重条件を設定できる「linear-elastic-plus」という
ウィザードを追加するパッチを提供することとしました。

これにより、ウィザードのみで解析を行える状況が格段に広がることが
期待できます。

パッチの内容：
READMEファイル
./wizard_patch_README.txt

各ウィザード共通ファイル（弾性応力解析改追加及び他言語化のため）
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/common.py
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s/wizards/common.py

弾性応力解析（他言語化のため）
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/linear_static.py

弾性応力解析改
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/linear_static_plus.py
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s/wizards/linear_static_plus.py

熱伝導解析（他言語化のため）
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/linear_thermic.py

固有値解析（他言語化のため）
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/modal_analysis.py

Asterモジュール内Aster>>Wizardsメニュー表示部分
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/module.py

上記の各オリジナルファイル
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/modal_analysis.py.org
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/linear_thermic.py.org
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/common.py.org
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/wizards/linear_static.py.org
./SALOME-MECA-2014.1-LGPL/modules/ASTER_20141/lib/python2.7/site-packages/salome/aster_s_gui/module.py.org

日本語及び英語各ライブラリQMファイル
./SALOME-MECA-2014.1-LGPL/modules/GUI_SALOME-MECA-2014.1-LGPL/share/salome/resources/gui/Aster_msg_ja.qm
./SALOME-MECA-2014.1-LGPL/modules/GUI_SALOME-MECA-2014.1-LGPL/share/salome/resources/gui/Aster_msg_en.qm

環境設定XMLファイル
（変更後）
./SALOME-MECA-2014.1-LGPL/modules/GUI_SALOME-MECA-2014.1-LGPL/share/salome/resources/gui/LightApp.xml

（オリジナル）
./SALOME-MECA-2014.1-LGPL/modules/GUI_SALOME-MECA-2014.1-LGPL/share/salome/resources/gui/LightApp.xml.org

インストール方法：
Salom-Mecaインストールディレクトリで当tarファイルを解凍するのみです。

% cd <Salome-Meca インストールディレクトリ>
% tar xvzf <ダウンロード先>/AsterWizards_linear_elastic_plus_005_with_toJpPatch_005_cr.tgz

使用方法：

日本語GUIへの変更方法>
Salome-Mecaの設定から言語設定をjaにすることで、既存ウィザード及び
「弾性応力解析改」を日本語GUIに変更できます。

メニュー>>ファイル（File）>> 環境設定（Preference）>> ja


弾性応力解析改>
「弾性応力解析改」は、Asterモジュール内メニューAsterの中にある
ウィザードに追加されております。

Asterに切り替え後
メニュー>>Aster>>Wizards>>弾性応力解析改


作成者：　Salome-Meca活用研究会　日本語化分科会メンバ
　　　　（代表　杉本　健）

作成日：2014/03/12
公開日：2014/06/01




