﻿---
title: ギャラリー ビューの構成
TOCTitle: ギャラリー ビューの構成
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48272007
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ギャラリー ビューの構成

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、会議ポリシーを使用してギャラリー ビューのビデオ会議を構成します。ギャラリー ビューは既定で有効になっています。ギャラリー ビューを許可しない場合、または一部のユーザーにのみ許可する場合は、会議ポリシーを使用して機能を無効にする必要があります。

会議参加者のビデオを利用できないときは、Lync Server 2013 の新機能である高解像度の写真を配置すると、ユーザーのギャラリー ビューの操作性を拡張できます。高解像度の写真は、Active Directory ドメイン サービス に格納されている小さく、解像度が制限された連絡先用の写真の代わりとなるものです。高解像度の写真は、ユーザーの Exchange 2013 メールボックスに格納されるため、Lync Server 2013 を Exchange 2013 と統合する必要があります。詳細については、NextHop ブログの記事「Integrating Exchange 2013 and Lync Server 2013」([http://go.microsoft.com/fwlink/?linkid=260987\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=260987%26clcid=0x411)」を参照してください。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>各ブログの内容と URL は、将来予告なしに変更されることがあります。</td>
</tr>
</tbody>
</table>


Lync Server 2013 コントロール パネルを使用するか、次のコマンドレットの 1 つを使用して、ギャラリー ビューのパラメーターを表示または変更できます。

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

次の会議ポリシー設定を使用してギャラリー ビューを構成します。

  - **AllowMultiview**   このパラメーターでは、ユーザーがギャラリー ビューのビデオ会議を開催できるかどうかを管理します。このパラメーターは、ユーザーによって作成されたケジュール済みの会議および臨時の会議に適用されます。
    
    例:
    
      - Lync Server 2013 プールに所属するユーザー A については、このパラメーターは True に設定されます。ユーザー A が開催する会議では、ユーザーは会議に参加し複数のビデオ ストリームを受信できます。
    
      - Lync Server 2013 プールに所属するユーザー B については、このパラメーターは False に設定されます。ユーザー B が開催する会議では、Lync Server 2010 が提供するビデオ会議エクスペリエンスと同様に単一のビデオ ストリームを使用します。
    
    このパラメーターにより、複数のビデオ ストリームが許可される会議を開催できるユーザーが決定します。複数のビデオ ストリームが許可される会議の参加者は、個々のアクセス許可に応じて、複数のビデオ ストリームを受信できたりできなかったりします (EnableMultiviewJoin パラメーターの説明を参照してください)。

  - **EnableMultiviewJoin**   このパラメーターでは、会議の参加者が、ギャラリー ビューのビデオ エクスペリエンスが許可されている会議でギャラリー ビューのビデオ エクスペリエンスを受け入れるかどうかを管理します。このパラメーターは、ユーザーが参加する会議でのユーザー エクスペリエンスを管理します。
    
    例:
    
      - ユーザー C については、このパラメーターは True に設定されます。ユーザー Ｃ は、ユーザー A が開催または開始した会議に参加しているときは、複数のビデオ ストリームを受信できます。ユーザー C は、ユーザー B が開催または開始した会議に参加しているときは、Lync Server 2010 が提供するビデオ会議エクスペリエンスと同様に単一のビデオ ストリームを受信します。
    
      - ユーザー D については、このパラメータは False に設定されます。ユーザー D は、ユーザー A またはユーザー B が開催した会議に参加しているときは、Lync Server 2010 が提供するビデオ会議エクスペリエンスと同様に単一のビデオ ストリームを受信します。

次の手順は、Lync Server 管理シェルを使用してギャラリー ビューのビデオ会議を有効にします。

## ギャラリー ビューのビデオ会議用の会議ポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ラインで次のコマンドレットを実行して、会議ポリシーを編集します。
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true

