---
title: 'Lync Server 2013: создание или изменение объекта контакта устройства конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d594f0bf6e393545f4a7c29785b5f66b328bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Создание или изменение объекта контакта устройства конференц-связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-10-02_

Чтобы создать объект комнаты конференц-связи, сначала создайте учетную запись пользователя Active Directory для представления устройства. Затем используйте командлет **Enable-ксмитингрум** , чтобы разрешить этой учетной записи работать в качестве устройства конференций. Если вам нужно изменить свойства существующего устройства конференц-связи, используйте командлет **Set – ксмитингрум** .

Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.

<div>


> [!NOTE]  
> Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Создание устройства конференц-связи

  - После создания учетной записи пользователя Active Directory, которая представляет новое устройство для проведения конференций, включите ее с помощью командлета **Enable-ксмитингрум** . Убедитесь в том, что вы хотите добавить учетную запись, b) в пул регистраторов, в котором будет храниться счет комнаты и c) адрес SIP, назначаемый этой учетной записи. Например:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Изменение устройства конференц-связи

  - Чтобы изменить значения свойств существующего устройства конференции, используйте командлет **Set-ксмитингрум** . Например, следующая команда обновляет номер телефона (Линеури), связанный с устройством конференц-связи:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Подробные сведения можно найти в разделах справки по командлетам [Enable-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) и командлету [Set-ксмитингрум](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

