---
title: 'Lync Server 2013: Get-CsWebServiceConfiguration для управления адресной книгой'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsWebServiceConfiguration for Address Book management
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429692(v=OCS.15)
ms:contentKeyID: 48183372
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 143b4964de91c10f2fce0272d6e882ff68c9f862
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512636"
---
# <a name="get-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Get-CsWebServiceConfiguration — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный  командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Командлет Get-CsWebServiceConfiguration возвращает сведения о конфигурации веб-служб, которая в данный момент используется в организации. С точки зрения служб адресной книги интерес представляет состояние функции расширения списка рассылки. Если атрибут EnableGroupExpansion имеет значение True, ваша организация допускает углубление в группы.

Например:

    Get-CsWebServiceConfiguration -Identity site:Redmond

<div>

## <a name="see-also"></a>См. также


[Get — CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

