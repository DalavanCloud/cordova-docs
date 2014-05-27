---

免許証: アパッシュ ソフトウェア基礎 (ASF) を 1 つまたは複数の共同作成者のライセンス契約の下でライセンスされています。 著作権所有権に関する追加情報のためのこの仕事と分散 NOTICE ファイルを参照してください。 ASF は、Version 2.0 (「ライセンス」）; Apache ライセンスの下であなたにこのファイルをライセンスします。ライセンスに従う場合、このファイルを使用可能性があります。 ライセンスのコピーを入手した可能性があります。

           http://www.apache.org/licenses/LICENSE-2.0 ライセンスの下で配布されるソフトウェアで配布されて適用される法律によって必要なまたは書面で合意した、しない限り、"AS IS"なしの保証または条件、いかなる種類の明示的または黙示的、基礎。  アクセス許可と制限を支配する特定の言語用のライセンスを参照してください。
    

## ライセンス。

# アマゾン火 OS プラットフォーム ガイド

このガイドの Kindle 火災 HDX などのアマゾン火 OS デバイス Cordova アプリを展開する SDK の開発環境を設定する方法を示します。

詳細なプラットフォーム固有の情報は、次を参照してください。

*   アマゾン火 OS 構成
*   アマゾン火 OS web 表示
*   アマゾン火 OS プラグイン

## 要件、およびサポート

アマゾン火 OS 用 Cordova アプリの開発には Android の SDK とアマゾン WebView SDK が必要です。以下のリンクでこれらの Sdk の要件を確認してください。

*   [Android の SDK システム][1]

*   [アマゾン WebView SDK][2]

 [1]: http://developer.android.com/sdk/
 [2]: https://developer.amazon.com/sdk/fire/IntegratingAWV.html#installawv

## インストール

### Android の SDK

[Developer.android.com/sdk][1]から Android SDK をインストールします。 それ以外の場合、ダウンロードした移動、SDK をインストールする場所の選択肢が表示されます `adt-bundle` ツリーの開発ツールを格納する場所を。

コルドバ動作するコマンド ライン ツール、SDK の含まする必要があります `tools` と `platform-tools` パス環境のディレクトリ。

Mac、Linux または他の Unix ライクなプラットフォームで、テキストエディターを使用して作成または変更することができます、 `~/.bash_profile` ファイルは、SDK のインストールに応じて、次のような行を追加します。

    エクスポート パス ${path} を =:/開発/adt-バンドル/sdk/プラットフォーム固有のツール:/開発/adt-バンドル/sdk/ツール
    

これは、SDK で新しくオープンしたターミナル windows のツールを公開します。それ以外の場合、現在のセッションで使用できるようにするこれを実行します。

    $ ソース ~/.bash_profile
    

Windows 7 を道の環境を変更: する

*   デスクトップの左下隅の [**スタート**] メニューをクリックして、**コンピューター**を右クリックし、**プロパティ**をクリックします.

*   左側の列では、**システムの詳細設定**をクリックします。

*   表示されたダイアログ ボックスで**環境変数**キーを押します。.

*   **パス**変数を選択し、キーを押して**編集**.

*   たとえば、SDK をインストールしたに基づくパスに次を追加します。
    
        ;C:\Development\adt-bundle\sdk\platform-tools;C:\Development\adt-bundle\sdk\tools
        

*   値を保存して両方のダイアログ ボックスを閉じます。

また、コマンド ・ プロンプトとタイプ Java および Ant. オープンを有効にする必要があります `java` 、また入力と `ant` 。パスに追加いずれかを実行する失敗します。

    ;%JAVA_HOME%\bin;%ANT_HOME%\bin
    

### アマゾン WebView SDK

[Amazon 開発者ポータル][2]からアマゾン WebView SDK をダウンロードします。.

*   作成、 `libs/` フォルダーに `~/.cordova/lib/amazon-fireos/cordova/3.1.0/` フォルダー。
*   追加の `awv_interface.jar` をダウンロードした SDK から`~/.cordova/lib/amazon-fireos/cordova/3.1.0/libs/`

## SDK でプロジェクトを開く

使用、 `cordova` コルドバのコマンド ライン インターフェイスで説明されているように、新しいプロジェクトを設定するユーティリティ。たとえば、ソース コード ディレクトリ: で

    $ cordova create hello com.example.hello "HelloWorld"
    $ cd hello
    $ cordova platform add amazon-fireos
    $ cordova build
    

Once created, you can use the Eclipse that comes along with the Android SDK to modify it:

*   **Eclipse**アプリケーションを起動します。

*   **新しいプロジェクト**のメニュー項目を選択します。

*   表示されたダイアログ ボックスから**既存のコードから Android プロジェクト**を選択し、**次**キーを押します。 ![][3]

*   移動する `hello` 、または好みのディレクトリに作成した、プロジェクトし、 `platforms/amazon-fireos` サブディレクトリ。

*   **終了**キーを押します。.

 [3]: img/guide/platforms//eclipse_new_project.png

Eclipse ウィンドウが開いたら、未解決の問題を示す赤い**X**が表示されます。もしそうなら、この追加の手順を実行します。

*   プロジェクト ディレクトリを右クリックします。

*   結果**のプロパティ**] ダイアログ [ **Android**ナビゲーション ウィンドウから。

*   プロジェクトのビルド ターゲットは、インストールされている最高の Android の API レベルを選択します。

*   **[Ok]**をクリックします.

*   **クリーン****をプロジェクト**メニューから選択します。これは、プロジェクト内のすべてのエラーを修正する必要があります。

## デバイスへの配置します。

デバイスに直接アプリをプッシュするには、 [Android 開発者向けサイト][4]で説明されているようにあなたのデバイスで USB デバッグを有効にかどうかを確認し、ミニ USB ケーブルを使用してあなたのシステムにプラグインします。

 [4]: http://developer.android.com/tools/device.html

アプリをデバイスにプッシュするには、コマンド行から。

    $ cordova run amazon-fireos
    

Eclipse、内でプロジェクトを右クリックし、**人造人間アプリケーション → として実行**を選択します.

**注**: 現在、エミュレーターを介してテストはサポートされていませんアマゾン WebView ベースのアプリ。