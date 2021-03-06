﻿---
title: Lync Server 2013　サーバー ハードウェア プラットフォーム
TOCTitle: サーバー　ハードウェア プラットフォーム
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48273560
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013　用のサーバー ハードウェア プラットフォーム

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 管理ツールを実行する Lync Server 2013 サーバーの役割およびコンピューターでは、64 ビットのハードウェアが必要です。

Lync Server 2013 の展開で使用する具体的なハードウェアは、サイズおよび使用に関する要件によってさまざまです。ここでは、推奨ハードウェアについて説明します。これらは推奨値であり、要件ではありませんが、推奨値を満たさないハードウェアを使用すると、重大なパフォーマンスの問題やその他の問題が発生する可能性があります。

## 推奨されるハードウェア プラットフォーム

最適なパフォーマンスを得るために、下表に示した要件を満たすハードウェアを使用したサーバーで Lync Server を実行することをお勧めします。これらの要件に満たないハードウェアを使用すると、機能的な問題またはパフォーマンス低下が発生する可能性があります。これらのハードウェア要件は、以前のバージョンの Lync Serverよりも高いことに注意してください。その主な理由は、Lync Server 2013 ではすべてのフロントエンド サーバーで SQL Server を実行するためです。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>NIC チーミングがサポートされ、Lync Server に対して透過的である必要があります。詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming (コミュニケーション サーバーまたは Lync Server とネットワーク アダプターのチーミング)</a>」を参照してください。</td>
</tr>
</tbody>
</table>


### フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、常設チャット サーバー、常設チャット ストアと常設チャット コンプライアンス ストア (常設チャット サーバーのバック エンド サーバーの役割) の推奨ハードウェア

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>推奨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 ビット デュアル プロセッサ、ヘキサ コア、2.26 GHz 以上。</p>
<p>Intel Itanium プロセッサは、Lync Serverのサーバーの役割用としてはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>32 ギガバイト (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 8 台以上。</p>
<p>これらのディスクのうち 2 台を RAID 1、6 台を RAID 10 で使用してください。</p>
<p>- または -</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 8 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>フロント エンド サーバー、バック エンド サーバー、Standard Edition サーバー、および 常設チャット サーバー のデュアルまたはマルチ ホーム構成は、サポートされていません。<br />
オペレーティング システムに対して公開されておらず、サーバー ハードウェアの監視と管理のために使用されている ILO/DRAC/etc. 接続は、マルチ ホーム サーバーにならないため、サポートされています。</td>
</tr>
</tbody>
</table>

</div></li>
</ul></td>
</tr>
</tbody>
</table>


### エッジ サーバー、スタンドアロン仲介サーバー、およびディレクターの推奨ハードウェア

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>推奨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64 ビット デュアル プロセッサ、クアッド コア、2.0 GHz 以上。</p>
<p>- または -</p></li>
<li><p>64 ビット 4 ウェイ プロセッサ、デュアル コア、2.0 GHz 以上。</p></li>
</ul>
<p>Intel Itanium プロセッサは、Lync Serverのサーバーの役割用としてはサポートされていません。</p></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>16 ギガバイト (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10,000 RPM のハード ディスク ドライブで 72 GB 以上の空きディスク領域があるものを 4 台以上。</p>
<p>ディスクは 2 x RAID 1 構成である必要があります。</p>
<p>- または -</p></li>
<li><p>10,000 RPM の機械的ディスク ドライブ 4 台と同等のパフォーマンスを持つソリッド ステート ドライブ (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps 以上のデュアルポート ネットワーク アダプター 1 つ (2 つを推奨。その場合は 1 つの MAC アドレスと 1 つの IP アドレスのチーミングが必要)。エッジ サーバー では 2 つのネットワーク インターフェイスが必要。これらはスタンドアロンの仲介サーバー上でサポートされています。</p></li>
</ul>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ディレクター のデュアルまたはマルチ ホーム構成は、サポートされていません。<br />
オペレーティング システムに対して公開されておらず、サーバー ハードウェアの監視と管理のために使用されている ILO/DRAC/etc. 接続は、マルチ ホーム サーバーにならないため、サポートされています。</td>
</tr>
</tbody>
</table>

</div>
<p>エッジ サーバー は、デュアルポート ネットワーク アダプターである、1 Gbps 以上の 2 つのネットワーク インターフェイス (または ２ 組のペアになっているネットワーク アダプター (合計で 4 個)、各ペアは 1 つの MAC アドレスと 1 つの IP アドレスでチーミングされた状態 (合計で 2 組のペア)) を必要とします。</p>
<p>追加のネットワーク インターフェイス カード (NIC) のインストールにより、特定の PSTN IP アドレスの構成がスタンドアロンの 仲介サーバー でサポートされるようになります。</p></td>
</tr>
</tbody>
</table>

