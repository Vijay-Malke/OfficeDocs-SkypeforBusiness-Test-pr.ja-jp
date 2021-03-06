﻿---
title: アーカイブ用ストレージのセットアップ
TOCTitle: アーカイブ用ストレージのセットアップ
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48274088
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ用ストレージのセットアップ

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 のアーカイブ用ストレージには、次のものが含まれています。

  - **データ ストレージ** データ ストレージは IM コンテンツの格納に必要です。

  - **ファイル ストレージ** ファイル ストレージは会議コンテンツのデータ ストレージおよびファイル ストレージの格納に必要です。

## データ ストレージのセットアップ

Lync Server 2013 のアーカイブ用データ ストレージのセットアップ要件は、アーカイブ データの格納方法に応じて異なります。

  - Exchange ストレージを使用してアーカイブ データを格納するには、Lync Server 2013 のアーカイブを Exchange の展開に統合します。

  - アーカイブ データを格納するには、SQL Server データベース サーバーを個別にセットアップします。

## アーカイブ データ用の Exchange ストレージのセットアップ

アーカイブ データ用の Exchange ストレージをセットアップするには、Exchange の展開で Exchange 2013 を実行している必要があります。また、ユーザーのメールボックスが Exchange 2013 に所属し、それらがインプレース ホールド中である必要があります。Exchange 2013 の構成について詳しくは、Exchange の製品ドキュメントを参照してください。

## アーカイブ データのストレージ用 SQL Server データベースのセットアップ

展開を Exchange に統合しない限り、Lync Server 2013 でのアーカイブには、アーカイブ データを格納するための SQL Server データベース ソフトウェアが必要です。

SQL Server アーカイブ データベースでは、アーカイブ データベースをホストするコンピューターに SQL Server をインストールする必要があります。フロントエンド プールのバックエンド データベースに使用するものと同じ SQL インスタンスを使用できます。パフォーマンスを最大限に高めるために、中央管理ストアとは別のコンピューター上にアーカイブ データベースを展開する必要があります。Lync Server 2013コンポーネントの併置について詳しくは、「サポート」のドキュメントの「[Lync Server 2013 のサポートされるサーバーの併置](lync-server-2013-supported-server-collocation.md)」をご覧ください。

各データベース サーバーは、サポートされている SQL Server のバージョンを実行している必要があります。サポートされているバージョンについて詳しくは、「計画」のドキュメントの「[Lync Server 2013 のアーカイブの技術要件](lync-server-2013-technical-requirements-for-archiving.md)」をご覧ください。

アーカイブを展開し、有効化する前に、SQL Server プラットフォームを設定する必要があります。トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。インストール手順の一部を含め、データベースを後で作成することもできます。SQL Server の詳細については、SQL Server TechCenter ([http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x411)) を参照してください。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>既定のアーカイブ SQL サーバーのメンテナンス ジョブが、SQL Server のエージェント サービスの制御によってスケジュールで実行できるように、SQL Server のエージェント サービスの [スタートアップの種類] が [自動] に設定され、アーカイブ データベースを持つ SQL インスタンスに対して SQL Server のエージェント サービスが実行されていることを確認します。</td>
</tr>
</tbody>
</table>


## ファイル ストレージのセットアップ

アーカイブでは、フロントエンド プールまたは Standard Edition サーバーのセットアップ時に指定した Lync Server 2013 ファイル共有を使用します。アーカイブに使用するファイル共有を変更することはできません。サポートされるファイル ストレージ システムについて詳しくは、「サポート」のドキュメントの「[Lync Server 2013 のファイル記憶域のサポート](lync-server-2013-file-storage-support.md)」をご覧ください。

