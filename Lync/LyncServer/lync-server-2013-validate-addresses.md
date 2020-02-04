---
title: 'Lync Server 2013: Проверка адресов'
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Проверка адресов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

Прежде чем публиковать базу данных местоположений, необходимо проверить новые расположения в соответствии с основным адресом (МСАГ), который поддерживается внутренней магистральной или коммутируемой телефонной сетью (КТСОП) E9-1-1 поставщика услуг.

Подробные сведения о поставщиках услуг E9ных магистральных каналов SIP-1-1 можно найти [в разделе Выбор поставщика услуг E9-1-1 для Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Подробнее об проверке адресов можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - **Get-Кслиссервицепровидер**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Проверка адресов, хранящихся в базе данных местонахождения

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

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

