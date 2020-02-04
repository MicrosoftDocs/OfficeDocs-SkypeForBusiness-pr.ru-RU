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
ms.openlocfilehash: 5a57ea93af90176009fff43ed4dcca9f1880a658
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>Перенос пользователей в единое хранилище контактов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-15_

Пользовательские контакты автоматически переносятся на сервер Exchange 2013, когда пользователь:

  - Назначена политика пользовательских служб, у которой Уксалловед установлено значение true.

  - Была настроена с помощью почтового ящика Exchange 2013 и один раз вошел в почтовый ящик.

  - Войдите в систему с помощью клиента Lync 2013 с богатыми возможностями.

Если пользователь входит в систему с помощью клиента Lync 2010 или более ранней версии или пользователь не подключен к серверу Exchange 2013, политика служб пользователей игнорируется, а контакты пользователя остаются в Lync Server.

Чтобы определить, перенесены ли контакты пользователя, используйте один из указанных ниже способов.

  - На клиентском компьютере проверьте следующий раздел реестра:
    
    \_Пользовательское\\программное\\обеспечение\\для\\hKey\\\_Microsoft\\\<Office 15,0\>\\Lync SIP URL UCS
    
    Если контакты пользователя хранятся в Exchange 2013, в этом разделе содержится значение Инуксмоде со значением 2165.

  - Запустите командлет **Test-ксунифиедконтактсторе** . В командной строке оболочки Lync Server Management Shell введите:
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    Если **тест-ксунифиедконтактсторе** выполняется успешно, контакты пользователя были перенесены в единое хранилище контактов.

</div>

<span> </span>

</div>

</div>

</div>

