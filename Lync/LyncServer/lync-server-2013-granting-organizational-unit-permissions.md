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
ms.openlocfilehash: d17715718d66530686009fdc4b2b9e2acebfceaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498906"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Предоставление разрешений организационных подразделений в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-05-14_

Вы можете использовать командлет **Grant-CsOuPermission**, чтобы предоставлять разрешения для объектов в указанных подразделениях, чтобы участники универсальных групп, созданных при подготовке леса, могли получать к ним доступ, не входя в группу администраторов домена. Разрешения, добавляемые к указанному подразделению — это те же разрешения, которые командлет **Enable-CsAdDomain** добавляется для компьютеров и контейнеров пользователей при подготовке домена.

С помощью командлета **Test-CsOuPermission** можно проверить разрешения, заданные с использованием командлета **Grant-CsOuPermission**.

Вы можете использовать командлет **Revoke-CsOuPermission** для удаления разрешений, предоставленных с помощью командлета **Grant-CsOuPermission**.

<div>

## <a name="to-grant-ou-permissions"></a>Предоставление разрешений для подразделения

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите предоставить разрешения для подразделения. Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если не указать параметр Domain, значением по умолчанию является локальный домен.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>Проверка разрешений для подразделения

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором необходимо проверить разрешения OU, предоставленные с помощью командлета **Grant – CsOuPermission** . Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если не указать параметр Domain, значением по умолчанию является локальный домен.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>Отзыв разрешений для подразделения

1.  Войдите на компьютер, на котором работает Lync Server 2013, в домене, в котором вы хотите отозвать разрешения OU, которые были предоставлены командлетом **Grant – CsOuPermission** . Используйте учетную запись, которая является членом группы администраторов домена или группы администраторов предприятия, если подразделение находится в другом дочернем домене.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Если не указать параметр Domain, значением по умолчанию является локальный домен.

</div>

</div>

<span> </span>

</div>

</div>

</div>

