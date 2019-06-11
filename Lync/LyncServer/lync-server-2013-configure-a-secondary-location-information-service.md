---
title: 'Lync Server 2013: Настройка дополнительной службы сведений о расположении'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8219aa234330120e6462a600b9c2c27b4b11c100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Настройка дополнительной службы сведений о расположении в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-30_

Lync Server 2013 предоставляет интерфейс веб-службы, который можно использовать для указания службы сведений о расположении в базу данных дополнительного расположения (СЛС). Интерфейс веб-службы, который подключается к базе данных СЛС, должен соответствовать WSDL службы сведений о расположении. Если вы настроили базу данных расположения и дополнительную базу данных расположения, Служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадений не найдено, отправляет запрос на расположение от клиента в базу данных СЛС. Если расположение находится в СЛС, служба сведения о местоположении затем отправляет клиенту расположение обратно.

Подробности можно найти в документации по оболочке управления Lync Server для следующего командлета:

  - **Set-Ксвебсервицеконфигуратион**

<div>

## <a name="to-configure-secondary-location-database"></a>Настройка дополнительной базы данных расположения

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

