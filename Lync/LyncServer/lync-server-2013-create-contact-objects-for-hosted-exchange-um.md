---
title: 'Lync Server 2013: создание объектов Contact для размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051b7f483ec3e3a59d5025c670b63b97765016b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532306"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

В этом разделе описывается создание контактных объектов автосекретаря или абонентского доступа для размещенной единой системы обмена сообщениями Exchange.

Дополнительные сведения: [Управление контактными объектами размещенного Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) в документации по планированию.

Для получения дополнительных сведений о настройке объектов Contact обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set — CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Перед тем как можно будет включить поддержку объектов контактов для размещенной единой системы обмена сообщениями Exchange Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним. Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Создание контактных объектов автосекретаря или абонентского доступа для размещенной единой системы обмена сообщениями Exchange

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать любой контактный объект, необходимо выполнить командлет New-CsExUmContact. Например, для создания контактного объекта автосекретаря и абонентского доступа выполните следующие командлеты:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    В этих примерах используются следующие параметры:
    
      - **SipAddress** указывает SIP-адрес контактного объекта. В качестве значения необходимо использовать адрес, который еще не использовался для настройки пользователя или контактного объекта в доменных службах Active Directory. Это значение должно быть в формате SIP:, \<*SIP address*\> как показано в предыдущих примерах.
    
      - **RegistrarPool** указывает полное доменное имя пула, в котором выполняется служба регистратора.
        
        <div class=" ">
        

        > [!NOTE]  
        > Объекты контактов Exchange единой системы обмена сообщениями невозможно переместить в пулы, которые входят в состав развертываний Lync Server 2013 до Lync Server 2013.

        
        </div>
    
      - **OU** задает подразделение Active Directory, в котором будет находиться данный контактный объект.
    
      - **DisplayNumber** указывает номер телефона контактного объекта. Номер телефона для каждого контактного объекта должен быть уникальным.
    
      - **AutoAttendant** указывает, является ли данный контактный объект автосекретарем. Автосекретарь предоставляет набор голосовых приглашений, которые позволяют звонящим перемещаться по телефонной системе, чтобы найти требуемого абонента. Значение **False** (по умолчанию) для этого параметра указывает контактный объект абонентского доступа.

</div>

</div>

<span> </span>

</div>

</div>

</div>

