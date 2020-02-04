---
title: 'Lync Server 2013: импорт правил обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872f729584f14011d18920a676c32205d38c7f62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Импорт правил обновления устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Правила обновления устройства можно импортировать только с помощью Windows PowerShell и командлета **Import-ксдевицеупдате** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Импорт правил обновления устройств на один веб-сервер

  - Следующая команда импортирует правила обновления устройств на веб-сервер atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Импорт правил обновления устройств на все веб-серверы

  - В этом примере правила обновления устройства импортируются на все веб-серверы, развернутые в Организации. Для работы этой команды необходимо предоставить общий доступ \\ \\к\\папке ATL-FS-001.litwareinc.com Updates и сделать ее доступной для всех веб-серверов.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Import-ксдевицеупдате](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>См. также


[Просмотр сведений о правилах обновления устройств в Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Утверждение правила обновления устройства в Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

