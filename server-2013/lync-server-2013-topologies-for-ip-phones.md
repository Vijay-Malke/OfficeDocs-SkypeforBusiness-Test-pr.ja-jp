﻿---
title: IP 電話用のトポロジ
TOCTitle: IP 電話用のトポロジ
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48271592
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IP 電話用のトポロジ

 

_**トピックの最終更新日:** 2012-06-21_

ここでは、接続プロセスの概要を示し、内部ネットワークと外部ネットワークでの IP 電話の接続方法の違いを説明します。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync Server でサポートされている IP 電話は、Aastra 6721ip 共通領域電話、Aastra 6725ip 卓上電話、HP 4110 IP 電話 (共通領域電話)、HP 4120 IP 電話 (卓上電話)、Polycom CX600 IP 卓上電話、Polycom CX700 IP 卓上電話、Polycom CX500 IP 共通領域電話、および Polycom CX3000 IP 会議電話です。これらの電話の中で、Polycom CX700 以外のすべての電話では Lync Phone Edition を実行できます。</td>
</tr>
</tbody>
</table>


次の図では、企業環境内でのデバイス接続に関係するすべてのコンポーネントを説明します。

**内部トポロジ**

![デバイスの内部ネットワーク](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "デバイスの内部ネットワーク")

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>前の図は論理的な表現であり、物理的な概要ではありません。たとえば、Active Directory ドメイン サービス (AD DS) が Lync Server のコンポーネントと同じコンピューターに配置されることはほとんどありません。ユーザー ストアは、バックエンド サーバー上、またはアーカイブ サーバーおよび監視サーバー上に配置できます。Lync Server 管理シェル、Web サーバー、および更新サービスは、すべて、フロントエンド サーバーの役割の一部です。</td>
</tr>
</tbody>
</table>


次の図では、デバイスが企業ネットワークの外部に配置される場合に関係するコンポーネントの概要を示します。

**外部トポロジ**

![デバイスの外部ネットワーク](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "デバイスの外部ネットワーク")

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>デバイス更新 Web サービスは、外部および内部の Web サイトを提供しますが、ここでは外部の Web サイトだけを示しています。<br />
外部アクセスを有効にする場合は、レジストラーの場所、および組織に対するデバイス更新 Web サービスの URL を DNS で公開する必要があります。さらに、エッジ サーバーを展開し、デバイスと企業環境の間の双方向の外部通信を許可するように適切に構成する必要があります。エッジの展開がデバイスの接続に固有ではないので、前の図ではこれは省略されています。</td>
</tr>
</tbody>
</table>

