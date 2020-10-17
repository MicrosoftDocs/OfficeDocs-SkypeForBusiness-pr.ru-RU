---
title: 'Lync Server 2013: Управление объектами контактов размещенного сервера Exchange'
description: 'Lync Server 2013: Управление объектами контактов размещенного сервера Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691bcea10d3a4f8b523c6565f384d6c4c9a2a2a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552775"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Управление объектом контакта размещенного сервера Exchange в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-25_

Необходимо настроить контактный объект для каждого номера автосекретаря и кода доступа в распределенном развертывании.

Для интеграции с размещенной единой системой обмена сообщениями Exchange ocsumutil.exe не может использоваться для управления контактными объектами, поскольку оно зависит от параметров единой системы обмена сообщениями Exchange в Active Directory. В распределенном развертывании Lync Server 2013 и размещенная единая служба обмена сообщениями Exchange устанавливаются в отдельных лесах без доверия между ними. Из соображений безопасности Lync Server 2013 администраторы не имеют прямого доступа к параметрам Active Directory единой системы обмена сообщениями Exchange. В результате Lync Server 2013 предоставляет другую модель для управления контактными объектами в *общем адресном пространстве SIP* , доступном как в Lync Server 2013, так и в размещенной службе единой системы обмена сообщениями Exchange.

<div>

## <a name="hosted-contact-object-workflow"></a>Рабочий процесс размещенных контактных объектов

Далее приводятся общие действия для совместной работы с администратором клиента размещенного Exchange по управлению контактными объектами.

1.  Администратор Exchange запрашивает телефонные номера для доступа абонентов единой системы обмена сообщениями Exchange и контактные объекты автосекретаря.

2.  Администратор Lync Server 2013 создает объект Contact для каждого номера телефона и назначает политику размещенной голосовой почты каждому объекту контакта.

3.  Администратор Lync Server 2013 предоставляет номера телефонов администратору Exchange.

4.  Администратор Exchange назначает эти телефонные номера соответствующим абонентским группам единой системы обмена сообщениями Exchange для автосекретарей и абонентского доступа.

<div>


> [!NOTE]  
> Нет необходимости настраивать параметры абонентской группы Lync Server 2013 для объектов Contact, как и в случае с локальными развертываниями.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Настройка размещенных контактных объектов

<div>


> [!NOTE]  
> Перед тем как можно будет включить поддержку объектов контактов для размещенной единой системы обмена сообщениями Exchange Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним. Эта политика может быть задана на глобальном уровне, на уровне сайта или на уровне пользователя, если она применяется к контактному объекту, который требуется включить. Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

Для настройки размещенных контактных объектов автосекретаря и абонентского доступа в распределенном развертывании необходимо использовать следующие командлеты:

  - **New-CsExUmContact**, который создает новый контактный объект для размещенной единой системы обмена сообщениями;

  - **Set-CsExUmContact**, который изменяет существующий контактный объект для размещенной единой системы обмена сообщениями Exchange.

В следующем примере создается контактный объект автосекретаря:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

В этом примере создается новый контактный объект единой системы обмена сообщениями Exchange с SIP-адресом sip:exumaa1@fabrikam.com. Имя пула, в котором работает служба регистратора Lync Server 2013, — RedmondPool.litwareinc.com. Сведения будут сохраняться в подразделении Active Directory OU=ExUmContacts,DC=litwareinc,DC=com. Телефонный номер контактного объекта — 2065554567. Дополнительный параметр -AutoAttendant $True указывает, что этот объект является контактным объектом автосекретаря. Значение False параметра -AutoAttendant (установленное по умолчанию) указывает контактный объект абонентского доступа.

Сведения о командлетах New-CsExUmContact и Set-CsExUmContact содержатся в документации по консоли управления Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

