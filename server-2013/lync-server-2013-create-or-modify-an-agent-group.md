﻿---
title: 'Lync Server 2013: エージェント グループの作成または変更'
TOCTitle: エージェント グループの作成または変更
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48273964
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 エージェント グループの作成または変更

 

_**トピックの最終更新日:** 2014-02-07_

エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>CsVoiceAdministrator などの管理者が、エンタープライズ VoIP および Lync Server のユーザーをエージェント グループに割り当てられるようにするには、これらのユーザーを有効にする必要があります。管理ワークフローの委任された応答グループ マネージャーであれば、エージェント グループを作成し、管理するワークフローでそのグループを使用できます。</td>
</tr>
</tbody>
</table>



> [!IMPORTANT]
> ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを伝えてください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。



## Lync Server コントロール パネル を使用してエージェント グループを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。</td>
    </tr>
    </tbody>
    </table>


2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**応答グループ**\] をクリックし、\[**グループ**\] をクリックします。

4.  \[**グループ**\] ページで、次のいずれかの操作を行います。
    
      - 新規エージェント グループを作成するには、\[**新規**\] をクリックします。\[**サービスの選択**\] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前のすべてまたは一部を入力します。サービスの結果一覧で、対象のサービスをクリックして \[**OK**\] をクリックします。
    
      - 既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前のすべてまたは一部を入力します。結果一覧で、対象のグループをクリックして、\[**編集**\] をクリックし、\[**詳細の表示**\] をクリックします。

5.  \[**名前**\] に、エージェント グループの識別名を入力します。

6.  \[**説明**\] に、グループの説明を入力します。

7.  \[**参加ポリシー**\] で、以下のいずれかを選択してグループのサインイン動作を設定します。
    
      - グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、\[**非公式**\] を選択します。エージェントは Lync Server 2013 にサインインするとそのグループに自動的にサインインします。
    
      - グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、\[**公式**\] を選択します。このオプションを選択すると、エージェントが Lync のメニュー項目をクリックして、Internet Explorer を開き、グループのサインイン/サインインアウトに使用する Web ページのコンソールを表示します。

8.  \[**警告時間 (秒)**\] で、次の有効なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。
    

    > [!IMPORTANT]
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。



9.  \[**ルーティング方法**\] で、グループのエージェントに通話をルーティングする方法を次のように指定します。
    
      - アイドルの最も長い ( Lync Server 上で \[**利用可能**\] または \[**非アクティブ**\] の状態が最も長い) エージェントに新しい通話を最初に提供するには、\[**最長アイドル**\] をクリックします。
    
      - 新しい通話を、有効なすべてのエージェントに同時に提供するには、\[**パラレル**\] をクリックします。通話は、最初に受け付けたエージェントに送られます。
    
      - 新しい通話を各エージェントに順番に提供するには、\[**ラウンド ロビン**\] をクリックします。
    
      - 新しい通話を、常に \[**エージェント**\] リストでのリスト順でエージェントに提供するには、\[**シリアル**\] をクリックします。
    
      - 現在のプレゼンスにかかわらず、 Lync Server 2013 と 応答グループ アプリケーションに同時にサインインしているすべてのエージェントに新しい通話を提供するには、\[**アテンダント**\] をクリックします。エージェントとして構成されている Lync 2010 Attendant のユーザーには、待機中のすべての通話が表示され、待機通話に任意の順序で応対できます。通話は、最初に許可したエージェントに送信され、その後は Lync 2010 Attendant の他のユーザーには表示されません。

10. \[**エージェント**\] で、エージェント リストの作成方法を指定します。
    
      - エージェントのカスタム リストを使用するには、\[**エージェントのカスタム グループを定義する**\] をクリックして、次のいずれかの操作を行います。
        
          - ユーザーをエージェント グループに追加するには、\[**選択**\] をクリックして \[**エージェントの選択**\] 検索フィールドで、このグループに追加するユーザーの名前または名前の一部を入力して \[**検索**\] をクリックします。エージェントの結果リストで、ユーザーをクリックして \[**OK**\] をクリックします。
        
          - エージェント グループからユーザーを削除するには、エージェントのリストで削除するユーザーをクリックし \[**削除**\] をクリックします。
        
          - ラウンド ロビン ルーティングまたはシリアル ルーティングのいずれかを使用するグループでエージェントが通話を提供される順序を変更するには、エージェントのリストで、ユーザーをクリックして上矢印または下矢印をクリックします。
    
      - Microsoft Exchange Server 配布リストをエージェント グループとして使用するには、\[**既存の電子メール配布リストを使用する**\] をクリックし、\[**配布リストのアドレス**\] に配布リストの電子メール アドレス (NetworkSupport@contoso.com など) を入力します。
        
        電子メール配布リストを使用する場合には、次の制約があります。
        
          - エージェント グループに対して複数の配布リストを選択することはできません。各グループでサポートされる配布リストは 1 つのみです。
        
          - 配布リストの中に別の配布リストが含まれている場合、入れ子となった配布リストのメンバーはエージェント リストに追加されません。
        
          - シリアルまたはラウンド ロビン ルーティングを選択した場合、着信通話はサーバーによってルーティング方法および配布リスト内のエージェントの順序に基づいて適切なエージェントに提供されます。
        
          - 配布リストのユーザーの中に、Lync Server 2010 は有効だが Enterprise Voice が無効なユーザーが含まれていると、それらのユーザーは機能しないエージェントとしてエージェント リストに追加されます。配布リストのすべてのメンバーのアカウントで、Enterprise Voice が有効であることを確認してください。
        

        > [!IMPORTANT]
        > 電子メール配布リストを使用する場合には、非表示のメンバーシップまたは非表示のリストが 応答グループの管理者またはユーザーに表示されることがあります。

        
        非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。
        
          - 配布リストが構成されメンバーシップが非表示になっている場合でも、 応答グループの管理者が配布リストをエージェント リストに割り当てていれば、ユーザーはメンバーを確認するためにグループを呼び出しできます。
        
          - 配布リストが構成され Exchange のグローバル アドレス リストで非表示になっている場合、 応答グループの管理者は、自分が適切なユーザー権限やアクセス許可を持っていない場合でも、 応答グループプロセスが適切なユーザー権限およびアクセス許可を持っていれば、配布リストを表示してエージェント リストに割り当てることができる場合があります。

11. \[**確定**\] をクリックします。

## Windows PowerShell を使用してエージェント グループを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  新規エージェント グループを作成するには、 **New-CsRgsAgentGroup** を使用します。既存のエージェント グループを変更するには、 **Set-CsRgsAgentGroup** を使用します。コマンド ラインで、次のコマンドを実行します。
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    次に例を示します。
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    

    > [!IMPORTANT]
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。



4.  次のコマンドを実行して、エージェント グループが作成されたことを確認します。
    
        Get-CsRgsAgentGroup -Name "Help Desk"

## 関連項目

#### タスク

[エージェント グループの削除](lync-server-2013-delete-an-agent-group.md)  

#### その他のリソース

[応答グループ エージェント グループの管理](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

