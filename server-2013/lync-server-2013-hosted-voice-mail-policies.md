﻿---
title: 'Lync Server 2013: ホスト型ボイス メール ポリシー'
TOCTitle: ホスト型ボイス メール ポリシー
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48273705
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のホスト型ボイス メール ポリシー

 

_**トピックの最終更新日:** 2012-10-01_

*ホスト型ボイス メール ポリシー*は、メールボックスが Hosted Exchange サービスに配置されたユーザーに対して通話をどこにルーティングすべきかを Lync Server 2013 ExUM ルーティング アプリケーションに伝えます。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ホスト ボイス メール ポリシーが必要なのは、Hosted Exchange UM と Lync Server 2013 の統合だけです。内部設置型の Exchange UM との統合には必要ありません。</td>
</tr>
</tbody>
</table>


## ホスト ボイス メール ポリシーのスコープ

ホスト ボイス メール ポリシーのスコープでは、ポリシーが適用される階層レベルが指定されます。以下のスコープ レベルのホスト ボイス メール ポリシーを構成できます。

  - *グローバル* ポリシーは、Lync Server 2013 展開のすべてのユーザーに影響する可能性があります。Hosted Exchange UM へのアクセスが有効になっているユーザーに対してユーザー単位のポリシーが割り当てられていない場合、およびユーザーのサイトにサイト ポリシーが割り当てられていない場合には、グローバル ポーリシーが適用されます。グローバル ポリシーは Lync Server 2013 によってインストールされます。グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。

  - *サイト* ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。

  - *ユーザー単位の* ポリシーは、個々のユーザーやグループにだけ影響します。ユーザー単位のポリシーを適用するには、個々のユーザー、グループ、または連絡先オブジェクトにこのポリシーを明示的に割り当てる必要があります。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ほとんどの場合には、必要なホスト ボイス メール ポリシーは 1 つだけです。多くの場合には、必要に応じてグローバル ポリシーを変更できます。複数のホスト ボイス メール ポリシーを展開する場合には、展開するすべてのポリシーにユーザー単位のスコープがあります。</td>
</tr>
</tbody>
</table>


## ホスト ボイス メール ポリシーの属性

ボイス メール ポリシーでは、Hosted Exchange UM 実装へ送信される招待メッセージの要求 URI に Lync Server 2013 ExUM ルーティング アプリケーションによって挿入される 2 つの属性が定義されます。

  - **宛先 :** Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) です。この値は内部設置型の Lync Server エッジ サーバーでルーティングに使用されます。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Exchange Online の FQDN は exap.um.outlook.com です。</td>
    </tr>
    </tbody>
    </table>


  - **組織 :** Lync Server 2013 ユーザーのメールボックスが所属する Hosted Exchange UM サービスのテナント FQDN です。ボイス メール ポリシーには複数の組織が含まれていることがあります。ポリシーに複数の組織が含まれている場合には、この属性は Lync Server 2013 ユーザー メールボックスが所属する Exchange Server テナントのカンマ区切り一覧である必要があります。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Hosted Exchange UM サービスのテナント管理者が、宛先と組織の属性設定に必要な値を提供します。ポリシーを構成するには、New-CsHostedVoicemailPolicy コマンドレットを実行するか、または set-cshostedvoicemailpolicy コマンドレットを使用して既存のポリシー (例: グローバル ポリシー) を変更する必要があります。</td>
</tr>
</tbody>
</table>


ホスト ボイス メール ポリシーの管理の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - New-CsHostedVoicemailPolicy

  - set-cshostedvoicemailpolicy

  - Get-CsHostedVoicemailPolicy

## ユーザー単位のボイス メール ポリシーの割り当て

ホスト ボイス メール ポリシーがユーザー単位のスコープで定義されている場合には、ユーザー単位のスコープを明示的に割り当てる必要があります。Grant-CsHostedVoicemailPolicy コマンドレッドを実行して、ポリシーを個々のユーザーまたはグループに割り当てることができます。

ユーザー単位のホスト ボイス メール ポリシーの割り当てまたは削除の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

