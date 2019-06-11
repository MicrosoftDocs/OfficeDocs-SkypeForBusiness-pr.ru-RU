---
title: 'Lync Server 2013: создание объектов Contact для размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ce65ed39e67068fcd57aba1177ecb72f553ccf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Ниже описана процедура создания объектов контактов для автоматического ассистента (AA) и доступа к абонентам (SA) для единой системы обмена сообщениями Exchange.

Дополнительные сведения можно найти [в разделе Управление объектами контактных данных Exchange в среде Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) в документации по планированию.

Дополнительные сведения о настройке объектов контакта можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Прежде чем можно будет включить объект контакта Lync Server 2013 для размещенной единой системы обмена сообщениями Exchange, необходимо развернуть политику размещенной голосовой почты, которая применяется к ним. Подробнее смотрите в разделе <A href="lync-server-2013-hosted-voice-mail-policies.md">политики размещенной голосовой почты в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Создание объектов контактов AA или SA для размещенной единой системы обмена сообщениями

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет New-Ксексумконтакт, чтобы создать любые объекты контактов, необходимые для вашего развертывания. Например, чтобы создать объект AA и контакт SA, выполните указанные ниже действия.
    
       ```
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    В этих примерах устанавливаются следующие параметры:
    
      - **Сипаддресс** указывает адрес SIP объекта Contact. Это должен быть адрес, который еще не использовался для настройки объекта пользователя или контакта в доменных службах Active Directory. Это значение должно быть в формате SIP:\<*SIP Address*\>, как показано в предыдущих примерах.
    
      - **Регистрарпул** указывает полное доменное имя (FQDN) пула, на котором запущена служба регистратора.
        
        <div class=" ">
        

        > [!NOTE]  
        > Объекты контактов Exchange UM нельзя переместить в пулы, которые являются частью развертывания Lync Server 2013 до Lync Server 2013.

        
        </div>
    
      - **OU** . определяет подразделение Active Directory, в котором будет находиться этот объект контакта.
    
      - **Дисплайнумбер** указывает телефонный номер объекта контакта. Номер телефона для каждого объекта контакта должен быть уникальным.
    
      - **Автосекретарь** указывает, является ли объект контакта автосекретарем. Автосекретарь предлагает набор голосовых запросов, которые позволяют вызывающим абонентам перемещаться по телефонной системе и обращаться к ним, к которым нужно обратиться. Значение **false** (по умолчанию) для этого параметра указывает на объект контакта доступа абонента.

</div>

</div>

<span> </span>

</div>

</div>

</div>

