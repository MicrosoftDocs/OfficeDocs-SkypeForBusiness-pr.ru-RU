---
title: 'Lync Server 2013: Настройка параметров парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 644ec44d4086b0acc326e043cbf63d7ceb2c640c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Настройка параметров парковки вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Если вы не хотите использовать параметры парковки вызовов по умолчанию, их можно настроить. При установке приложения парковки вызовов глобальные параметры настраиваются по умолчанию. Вы можете изменять глобальные параметры, а также задавать параметры для конкретных сайтов. Используйте командлет **New-CsCpsConfiguration** для создания новых параметров, связанных с сайтом. Используйте командлет **Set – CsCpsConfiguration** для изменения существующих параметров.

<div>


> [!NOTE]  
> Мы рекомендуем вам настроить хотя бы параметр <STRONG>OnTimeoutURI</STRONG> для резервного назначения, используемого в случае истечения времени ожидания запаркованного вызова и сбоя переключения на удерживаемого абонента.



</div>

Используйте командлет **New-CsCpsConfiguration** или **Set-CsCpsConfiguration** для настройки любых из приведенных ниже параметров:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Данный параметр:</th>
<th>Указывает следующее:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>каллпиккуптимеаутсрешолд</strong></p></td>
<td><p>Период времени, по истечении которого припаркованный вызов перенаправляется обратно на номер телефона, с которого ответили на звонок.</p>
<p>Значение следует вводить в формате чч:мм:сс, где чч — это часы, мм — минуты, сс — секунды. Минимальное значение составляет 10 секунд, максимальное — 10 минут. Значение по умолчанию — 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>енаблемусиконхолд</strong></p></td>
<td><p>Воспроизводится ли музыка для звонящего при парковке вызова.</p>
<p>Доступны значения True и False. Значение по умолчанию — True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>макскаллпиккупаттемптс</strong></p></td>
<td><p>Число повторных звонков припаркованного вызова на ответивший телефон перед перенаправлением на резервный универсальный код ресурса (URI), указанный для <strong>OnTimeoutURI</strong>. Значение по умолчанию — 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>SIP-адрес пользователя или группы ответа, которым перенаправляется неотвеченный припаркованный вызов в случае превышения значения <strong>MaxCallPickupAttempts</strong>.</p>
<p>Значение должно быть кодом URI SIP. начинающимся со строки sip:. Например, sip:bob@contoso.com. По умолчанию адрес пересылки не используется.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Настройка параметров парковки вызовов

1.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Используйте командлет <STRONG>Get-CsSite</STRONG> для идентификации сайта. Дополнительные сведения см. в документации по командной консоли Lync Server.

    
    </div>
    
    Пример:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка музыки парковки вызовов на удержании в Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[New — CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set — CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get — CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

