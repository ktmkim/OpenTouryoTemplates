﻿# Open棟梁 Visual Studio2010 テンプレート・ベースの利用方法(How to Use OpenTouryo Visual Studio 2010 template base)


Open棟梁 Visual Studio2010 テンプレート・ベースに
同梱されるサンプルの実行手順は下記のとおりです。

(Execution procedure of the samples that are shipped with the
OpenTouryo Visual Studio 2010 template base is as follows.)

* 「/root_VS2010/」以下のフォルダを「C:\root」フォルダ以下に配置します。
   (Deploy to under 「C:\root」folder from under 「/root_VS2010/」folder.)
   
* Visual Studio 2010 と SQL Server のインストール
   (Installing Visual Studio 2010 and SQL Server.)
   
* サンプルDBの準備(Prepare Sample DB)

   - 下記からダウンロードしインストールします。
      (Download and install from the following.)
      
      Download: NorthWind and pubs Sample Databases for SQL Server 2000 - Microsoft Download Center - Download Details
      http://www.microsoft.com/download/en/details.aspx?displaylang=en&id=23654
      
   - 下記コマンドを実行します(Run the following command)。
      "C:\Program Files\Microsoft SQL Server\100\Tools\Binn\SQLCMD.EXE" -S localhost\SQLExpress -E -i "C:\SQL Server 2000 Sample Databases\instnwnd.sql"

* セッション状態サービスの準備(Preparing the session state service)
   - 管理者としてコマンドプロンプトを起動し、下記コマンドを実行します。
      (Start a command prompt as an administrator, and then run the following command.)
      
      sc config aspnet_state start= auto
      net start aspnet_state

* プログラムのビルド(Building the program)
   C:\root\programs\C#
   C:\root\programs\VB

   フォルダ以下のビルドバッチを番号順に実行してプログラムをビルドします。
   (Build the program by running in numerical order the build batch of Above folder.)

   - 必要であれば、環境に合わせて、z_Common.bat内のBUILDFILEPATHを書き換えます。
     (If necessary, for your environment, you can rewrite the BUILDFILEPATH of z_Common.bat within.)
   
     Express Editionを使用している場合は、devenv.comが存在しないので、
     z_Common.batとz_Common2.batを差し替えてMSBuild.exeを使用して下さい。
     
     (If you are using the Express Edition,
     use the MSBuild.exe by replacing the z_Common2.bat and z_Common.bat.
     Because devenv.com does not exist.)
   
   - VB版を使用する場合は、"C:\root\programs\C#\"の
     1_DeleteDir.batから4_Build_Framework_Tool.batまでを実行した後に、
     "C:\root\programs\VB\"の1_DeleteDir.batから順次実行して下さい。
     
     If you use the VB version,
     after executing from "1_DeleteDir.bat" to "4_Build_Framework_Tool.bat" at the location of "C:\root\programs\C#\",
     please executing sequentially from "1_DeleteDir.bat" at the location of "C:\root\programs\VB\".
     
* サンプルの実行(Running the Sample)

   下記ファイルを開き実行する（VB版は一部の提供になっています）。
   ログイン画面が出た場合は、パスワードの確認は行っていないため、任意の数字を入力してください。
   
   (Open and run the following file (VB version provide some). 
   If the login screen appears, because not check the password, please enter the number of any.)
   
   - Web の場合(In the case of Web)：
      - ASP.NET
         C:\root\programs\C#\Samples\WebApp_sample\ProjectX_sample\ProjectX_sample.sln
    
   - C/S 2階層の場合(In the case of two-tier C/S)：
      - Windows Forms
         C:\root\programs\C#\Samples\2CS_sample\2CSClientWin_sample\2CSClientWin_sample.sln
      - WPF
         C:\root\programs\C#\Samples\2CS_sample\2CSClientWPF_sample\2CSClientWPF_sample.sln
    
   - C/S 3階層の場合(In the case of three-tier C/S)：
      - Windows Forms
         C:\root\programs\C#\Samples\WS_sample\WSClient_sample\WSClientWin_sample\WSClientWin_sample.sln
         C:\root\programs\C#\Samples\WS_sample\WSClient_sample\WSClientWinCone_sample\WSClientWinCone_sample.sln
      - WPF
         C:\root\programs\C#\Samples\WS_sample\WSClient_sample\WSClientWPF_sample\WSClientWPF_sample.sln
         C:\root\programs\C#\Samples\WS_sample\WSClient_sample\WSClientWPFbap_sample\WSClientWPFbap_sample.sln
    
   - Silverlight の場(In the case of Silverlight)：
      C:\root\programs\C#\Samples\WS_sample\WSClient_sample\WSClientSL_samples\WSClientSL_samples.sln
   - Windows Azure の場合(In the case of Windows Azure)：
      C:\root_org\programs\C#\Samples\WinAzure_sample\WinAzure_sample.sln

* 各チュートリアルの内容に従いOpen棟梁の評価が可能です。
   (Evaluation of OpenTouryo is possible in accordance with the contents of each tutorial.)
   
   \OpenTouryoProject\OpenTouryoDocuments\2_Tutorial\
   
   ドキュメント類は[OpenTouryoProject/OpenTouryoDocuments](https://github.com/OpenTouryoProject/OpenTouryoDocuments)リポジトリに格納されています。
   (documents are located in the [OpenTouryoProject/OpenTouryoDocuments](https://github.com/OpenTouryoProject/OpenTouryoDocuments) repository.)
   
* また、テンプレート・ベースをチュートリアルの内容に従いカスタマイズすることで、
   当該Visual Studioバージョンの案件向けプロジェクト・テンプレートを作成できます。
   
   (Further, You  will customize template base according to the contents of the tutorial, 
   You can create project template for the Visual Studio version for the project.)
    
   \OpenTouryoProject\OpenTouryoDocuments\2_Tutorial\Tutorial_Template_development.doc
   
   ドキュメント類は[OpenTouryoProject/OpenTouryoDocuments](https://github.com/OpenTouryoProject/OpenTouryoDocuments)リポジトリに格納されています。
   (documents are located in the [OpenTouryoProject/OpenTouryoDocuments](https://github.com/OpenTouryoProject/OpenTouryoDocuments) repository.)
   
# 著作権、ライセンス(Copyright, license)

[License](https://github.com/OpenTouryoProject/OpenTouryoTemplates/tree/master/license)ディレクトリを確認下さい。
(Please check [License](https://github.com/OpenTouryoProject/OpenTouryoTemplates/tree/master/license) directory.)

# バグ対応(Bug fix)

バグの発見や通知があった場合、通知の妥当性の確認後、
バックログに加えられ任意のタイミングでフィックスされます。

バグ修正パッチの取込みは、最新版取込みにより実現されます。
若しくは、当該バグをトラッキング・ツール上から確認して
リポジトリからバグフィックス時のDIFFを取得し各自マージしてください。

If there is a notification or discovery of the bug,
after confirmation of the validity of the notification, 
It will be fixed at any time be added to the backlog. 

Incorporation of bug fixes are implemented by the latest version of incorporation. 
Or, check from the tracking tool on the bug 
Please have your own merge by get the DIFF of bug fixes from the repository at the time.

# データプロバイダの入手、輸出手続き、使用許諾への添付について(obtain the data provider. export procedures. attach to license.)

Open棟梁では、種々のデータ・プロバイダをサポートしていますが、
各データ・プロバイダの入手・輸出手続きに関しては、各自対応下さい。

The OpenTouryo is support the data provider of various, 
For information on obtaining and export procedures for each data provider, please support their own.
