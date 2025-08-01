# ペイントジョブパッカー
ペイントジョブパッカーは、Euro Truck Simulator 2およびAmerican Truck Simulator用の軽量MOD作成ツールです。これにより、複数の車両に対応するMODに焦点を当てた、シンプルなペイントジョブMODを生成できます。

本レポジトリは、https://github.com/Carsmaniac/paintjob-packer の日本語訳版になります。
友達共有用なので品質は知りません
## 機能

* DLCを含むプレイヤー所有のトレーラーをサポート
* Scania SやMAN TGX Euro 6など、新しいアクセサリーベースのペイントジョブシステムを使用するトラックをサポート
* 1つのMODで好きなだけ多くの車両をサポート
* 100以上のトラックおよびトレーラーMODを内蔵でサポート。全リストは[こちら](https://github.com/Carsmaniac/paintjob-packer/blob/master/library/mod%20links.md)
* 1つのテクスチャがすべてのキャビンで機能しない場合に備えて、トラックの各キャビンに個別のペイントジョブをサポート
* オプションで、各車両の4kテンプレートが付属しており、[こちら](https://forum.scssoft.com/viewtopic.php?f=33&t=272386) (ETS 2) および[こちら](https://forum.scssoft.com/viewtopic.php?f=199&t=288778) (ATS) から個別にダウンロードできます

## MODの作成

ペイントジョブパッカーは、「MODを生成」ボタンをクリックしても完成したMODを作成しません。代わりに、私が「カスタムサンプルMOD」と呼ぶものを作成します。これは、MODに必要なすべてのファイルを、すべての画像/テクスチャのプレースホルダーとして提供するものです。その後、すべてのプレースホルダー画像を自分のものに置き換えてMODを完成させます。通常、ペイントジョブが完成するまでに何度もテストと調整が必要になるため、この方法でペイントジョブを生成すると、プログラムを一度実行するだけで済みます。

このガイドのより詳細なビデオ版は[YouTubeで利用できます](https://www.youtube.com/watch?v=HJV8_X3P9k8)。

### 画像エディタの要件

ペイントジョブパッカーには、DDSファイルを保存できる画像エディタが必要です。DDSは、Trucksimゲームを含む多くのゲームでテクスチャを保存するために使用される特殊な画像形式です。以下のいずれかを使用できます。

* Photoshopと[DDSプラグイン](https://fnordware.blogspot.com/2014/09/dds-plug-in-for-after-effects-and.html)
* [GIMP](https://www.gimp.org/downloads/)
* [Paint.NET](https://www.getpaint.net/download.html)
* または、任意のプログラムを使用し、[DXTBmp](https://www.mwgfx.co.uk/programs/dxtbmp.htm)を使用して画像をDDSに変換することもできます

1.  ペイントジョブパッカーを使用してベースファイルを生成します
    * 単一の車両用の単一のペイントジョブ、または複数の車両をサポートするパックを作成します
    * 各トラックの最大のキャビンのみ、またはすべてのキャビンをサポートし、車両ごとに1つのペイントジョブまたは各キャビンに個別のペイントジョブを設定します
    * オプションで、4k/2kテンプレートをプレースホルダーファイルとして使用します（インストールされている場合）

2.  MODマネージャーファイルを置き換えます
    * `Mod_Manager_Description.txt` および `Mod_Manager_Image.jpg`
    * 説明には、MODでサポートされている車両の事前生成リストがすでに含まれています
    * 画像は276 x 162のJPEGである必要があります

3.  アイコンを置き換えます
    * `material/ui/accessory/<paint job> Icon.dds`
    * 256 x 64のDDSである必要があります
    * アイコンをバニラのペイントジョブに合わせたい場合は、プレースホルダー画像をサイズと形状のガイドとして使用してください

4.  車両のテクスチャを置き換えます
    * `vehicle/truck/upgrade/paintjob/<paint job>/<vehicle>` および/または `vehicle/trailer_owned/upgrade/paintjob/<paint job>/<vehicle>`
    * これらはMODの主要ファイルであり、ゲーム内でペイントジョブが実際にどのように見えるかを決定します
    * 可能であれば、各DDSをミップマップ付きのDXT5形式で保存してください
    * すべてのファイルの高さと幅が2の累乗（例：16、64、2048、4096など）であることを確認してください
    * テンプレートパックは[こちら](https://forum.scssoft.com/viewtopic.php?f=33&t=272386) (ETS 2) および[こちら](https://forum.scssoft.com/viewtopic.php?f=199&t=288778) (ATS) からダウンロードできます
