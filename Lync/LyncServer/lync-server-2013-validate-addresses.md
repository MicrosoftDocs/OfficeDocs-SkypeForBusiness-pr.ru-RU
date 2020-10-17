---
title: 'Lync Server 2013: Проверка адресов'
description: 'Lync Server 2013: Проверка адресов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547275"
---
# <a name="validate-addresses-in-lync-server-2013"></a>Проверка адресов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Перед публикацией базы данных местонахождений нужно проверить новые местонахождения в контрольном справочнике городских адресов, предоставляемом вашей магистралью SIP или поставщиком служб E9-1-1 ТСОП.

Подробные сведения о поставщиках услуг SIP E9 – 1 – 1 можно найти [в статье Выбор поставщика услуг E9 – 1 – 1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Для получения дополнительных сведений об проверке адресов обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - **Get — Кслиссервицепровидер**

  - **Set — Кслиссервицепровидер**

  - **Remove — Кслиссервицепровидер**

  - **Get — КслисЦивикаддресс**

  - **Test-КслисЦивикаддресс**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Проверка адресов, хранящихся в базе данных местонахождения

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы настроить подключение к поставщику экстренной службы, выполните следующие командлеты.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Чтобы проверить адреса, хранящиеся в базе данных местонахождения, выполните следующий командлет.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Кроме того, для проверки отдельных адресов вы можете использовать командлет **Test-CsLisCivicAddress**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

