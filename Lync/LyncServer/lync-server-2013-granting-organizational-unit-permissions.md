---
title: 'Lync Server 2013: предоставление разрешений организационного подразделения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Предоставление разрешений организационного подразделения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-05-14_

Командлет **Grant-ксаупермиссион** можно использовать, чтобы предоставить разрешения на доступ к объектам в указанных организационных подразделениях (OU) таким образом, чтобы пользователи универсальных групп RTC, созданные с помощью подготовки леса, могли получать к ним доступа, не прибегая к группе администраторов домена. Разрешения, добавленные в указанный ОРГАНИЗАЦИОНный элемент, являются теми же разрешениями, которые командлет **Enable-ксаддомаин** добавляет к контейнерам компьютеров и пользователей во время подготовки домена.

Используйте командлет **Test-ксаупермиссион** для проверки разрешений, настроенных с помощью командлета **Grant-ксаупермиссион** .

Командлет **REVOKE-ксаупермиссион** можно использовать для удаления разрешений, предоставленных с помощью командлета **Grant-ксаупермиссион** .

<div>

## <a name="to-grant-ou-permissions"></a>Предоставление разрешений на доступ к подразделению

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите предоставить разрешения на доступ к подразделению. Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если параметр Domain не указан, значение по умолчанию — локальный домен.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Проверка разрешений на доступ к подразделению

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите проверить разрешения на доступ к подразделению, предоставленные с помощью командлета **Grant-ксаупермиссион** . Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду:
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если параметр Domain не указан, значение по умолчанию — локальный домен.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Отмена разрешений на доступ к подразделению

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домен, в котором вы хотите отозвать разрешения на доступ к подразделению, предоставленные командлетом **Grant-ксаупермиссион** . Используйте учетную запись, которая входит в группу "Администраторы домена" или "Администраторы предприятия", если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду:
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если параметр Domain не указан, значение по умолчанию — локальный домен.

</div>

</div>

<span> </span>

</div>

</div>

</div>

