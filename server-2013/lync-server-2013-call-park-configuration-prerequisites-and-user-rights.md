﻿---
title: 'Lync Server 2013: コール パーク構成の前提条件とユーザー権限'
TOCTitle: コール パーク構成の前提条件とユーザー権限
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48271581
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコール パーク構成の前提条件とユーザー権限

 

_**トピックの最終更新日:** 2012-09-10_

コール パークは、エンタープライズ VoIP を展開する際に既定でインストールされる通話管理機能です。このトピックでは、コール パークの構成の前に用意しておく必要がある項目、および構成タスクの実行に必要なユーザー権限について説明します。


> [!IMPORTANT]
> コール パーク アプリケーション用のカスタマイズされた保留音ファイルは Lync Server 2013 の障害復旧プロセスの過程でバックアップされることはなく、プールにアップロードされているファイルが破損したり消去されたりした場合はファイルが失われます。コール パーク用にアップロードされていたカスタマイズされた保留音ファイルのバックアップ コピーを常に別途保管しておいてください。



ここでは、読者が コール パークに関する「計画」のドキュメントを読み終えていること前提に説明を進めます (「[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照)。

## コール パーク構成の前提条件

コール パークでは、次のコンポーネントが必要です。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズ VoIP を展開する際に自動でインストールされます。

通話の保留中に発信者が音楽を聞けるようにするには、保留音ファイルも必要です。既定の保留音ファイルは、エンタープライズ VoIP を展開する際に自動でインストールされます。既定のファイルを独自の保留音ファイルと入れ替えることができます。コール パークは、ファイル ストアを使用してオーディオ ファイルを保管します。

## コール パーク構成のユーザー権限

次の管理ツールを使用して コール パークを構成できます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

これらのツールを使用して コール パーク オービット テーブルを設定し、コール パークで使用される他の設定を構成します。

コール パークの構成には、タスクによって異なりますが、次の管理者の役割のいずれかが必要です。

  - **CsVoiceAdministrator :** この管理者の役割は、音声関連のすべての設定とポリシーを作成、構成、および管理できます。

  - **CsUserAdministrator :** この管理者の役割は、音声ポリシーで コール パークを有効にすることができます。また、すべての音声構成に対する読み取り専用の表示アクセス権を持ちます。

  - **CsServerAdministrator :** この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングできます。

  - **CsAdministrator :** この管理者の役割は、CsVoiceAdministrator、CsServerAdministrator、および CsUserAdministrator のすべてのタスクを実行できます。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>管理者権限の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a>」を参照してください。</td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 でのエンタープライズ VoIP の展開](lync-server-2013-deploying-enterprise-voice.md)  

#### その他のリソース

[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)

