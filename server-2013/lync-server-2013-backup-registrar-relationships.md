﻿---
title: 'Lync Server 2013: バックアップ レジストラー関係'
TOCTitle: バックアップ レジストラー関係
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48272649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のバックアップ レジストラー関係

 

_**トピックの最終更新日:** 2012-06-28_

障害復旧の機能を提供するほか、ペアになった 2 つのプールは互いにバックアップ レジストラーの役割も果たします。Lync Server 2013 では、フロント エンド プール間のバックアップ レジストラーの関係が常に 1 対 1 であり、相互的です。これは、P1 が P2 のバックアップであれば P2 が P1 のバックアップでなければならず、また双方がその他のいかなるフロントエンド プールのバックアップにもなれないことを意味します。この点は、フロント エンド プールのバックアップ関係が多対 1 になる可能性があった Lync Server 2010 からの変更部分です。

たとえ 2 つの フロント エンド プール間のバックアップ関係が 1 対 1 であって対称的でなければならないとしても、各 フロント エンド プールは依然として、Lync Server 2010 での場合のように、任意の数の 存続可能ブランチ アプライアンスのバックアップ レジストラーになる可能性があります。

Lync Server 2013 では、障害復旧のサポート対象に 存続可能ブランチ アプライアンスに所属するユーザーが含まれません。存続可能ブランチ アプライアンスのバックアップとしての役割を果たすフロントエンド プールがダウンした場合、存続可能ブランチ アプライアンスにサインインしていたユーザーは、フロントエンド プールに所属していたユーザーがバックアップの フロント エンド プールにフェールオーバーされた後でも、復元モードになります。
