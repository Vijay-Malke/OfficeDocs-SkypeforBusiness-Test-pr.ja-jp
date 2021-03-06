﻿---
title: ネットワーク メディア バイパスの無効化
TOCTitle: ネットワーク メディア バイパスの無効化
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49887054
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク メディア バイパスの無効化

 

_**トピックの最終更新日:** 2012-10-15_

メディア バイパス設定は、Microsoft Lync Server 2013 展開にグローバルに適用します。メディア バイパスによって、仲介サーバーによる通話のバイパスが可能になります。メディア バイパス使用時の詳細については、「計画」のセクションの「[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。メディア バイパスは Lync Server コントロール パネルから無効にできます。メディア バイパスの有効化と構成の詳細については、「[ネットワーク メディア バイパスの有効化](lync-server-2013-enabling-network-media-bypass.md)」を参照してください。

## メディア バイパスを無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**グローバル**\] をクリックします。

4.  \[**グローバル**\] ページで \[**グローバル**\] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**グローバル設定の編集**\] ページの \[**メディア バイパスを有効にする**\] チェック ボックスをオフにします。

7.  \[**確定**\] をクリックして変更を保存します。

## 関連項目

#### タスク

[ネットワーク メディア バイパスの有効化](lync-server-2013-enabling-network-media-bypass.md)

