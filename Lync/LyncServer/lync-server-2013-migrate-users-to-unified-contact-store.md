---
title: 'Lync Server 2013: перенос пользователей в единое хранилище контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d170fa183e045203398725a7b7ec4bdd4c38203
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Миграция пользователей в единое хранилище контактов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-15_

Контакты пользователя автоматически переносятся на сервер Exchange 2013 в следующих условиях.

  - пользователю назначена политика служб пользователя, где для параметра UcsAllowed установлено значение true;

  - Был подготовлен с помощью почтового ящика Exchange 2013 и выполнил вход по крайней мере один раз в почтовый ящик.

  - Выполняет вход с помощью полнофункционального клиента Lync 2013.

Если пользователь входит в систему с помощью клиента Lync 2010 или более ранней версии или если пользователь не подключен к серверу Exchange 2013, политика служб пользователя игнорируется, а контакты пользователя сохраняются в Lync Server.

Можно определить, перенесены ли контакты пользователя, с помощью любого из следующих методов:

  - Проверьте следующий раздел реестра на клиентском компьютере:
    
    Программное\_обеспечение\\\\для текущего\\пользователя\\hKey\\\_Microsoft\\\<Office 15,0\>\\Lync SIP URL-адрес UCS
    
    Если контакты пользователя хранятся в Exchange 2013, этот раздел содержит значение параметр inucsmode со значением 2165.

  - Выполните командлет **Test-CsUnifiedContactStore**. В командной строке Командная консоль Lync Server введите:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Если командлет **Test-CsUnifiedContactStore** выполнен успешно, следовательно, выполнен перенос контактов пользователя к единое хранилище контактов.

</div>

<span> </span>

</div>

</div>

</div>

