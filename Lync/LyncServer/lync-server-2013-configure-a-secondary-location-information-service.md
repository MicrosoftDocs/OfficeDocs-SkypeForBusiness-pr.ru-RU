---
title: 'Lync Server 2013: Настройка службы сведений о дополнительном местоположении'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50d63d8316c9ce18bdf8677686a655046601b326
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Настройка службы сведений о дополнительном местоположении в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

Lync Server 2013 предоставляет интерфейс веб-службы, который можно использовать для ссылки на службу сведений о местоположении в базу данных дополнительных источников расположения (SLS). Интерфейс веб-службы, который подключается к базе данных SLS, должен соответствовать WSDL-службе сведений о расположении. Если для базы данных расположения и базы данных дополнительных расположений настроена служба "сведения о местонахождении", сначала запрашивается база данных расположения, а если совпадения не найдены, отправляет запрос расположения от клиента в базу данных SLS. Если расположение существует в SLS, служба информационного расположения затем отправляет клиенту расположение обратно.

Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующего командлета:

  - **Set — CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Настройка базы данных дополнительных расположений

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните следующий командлет, чтобы настроить URL-адрес для расположения базы данных дополнительных расположений.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

