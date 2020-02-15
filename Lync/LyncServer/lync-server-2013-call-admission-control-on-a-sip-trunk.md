---
title: 'Lync Server 2013: контроль допуска звонков на магистральной линии SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ae55f6146e59931b55ec384d374ea837eeb598c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Контроль допуска звонков на магистральной линии SIP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-22_

Для развертывания контроля допуска звонков в канал SIP создается сетевой узел, который представляет поставщика услуг Интернет-телефонии (ITSP). Для применения значений политики пропускной способности в канале SIP создается межузловая политика между сетевым узлом в предприятии и сетевым узлом, созданным для представления ITSP.

На следующем рисунке показан пример развертывания контроля допуска звонков в канале SIP.

**Конфигурация контроля допуска звонков в канале SIP**

![Схема распределения каналов SIP управления допуском звонков](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Схема распределения каналов SIP управления допуском звонков")

Чтобы настроить контроль допуска звонков в канале SIP, во время развертывания контроля допуска звонков необходимо выполнить следующие задачи.

1.  Создать сетевой узел, представляющий поставщика услуг Интернет-телефонии (ITSP). Связать этот сетевой узел с соответствующей областью сети и выделить в этом сетевом узле нулевую пропускную способность для аудио и видео. Подробнее: [Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) в документации по развертыванию.
    
    <div>
    

    > [!NOTE]  
    > Для ITSP конфигурация этого сетевого узла не функциональна. Значения политики пропускной способности фактически применяются в шаге 2.

    
    </div>

2.  Создайте межсайтовую связь для магистрали SIP с использованием соответствующих значений параметров для сайта, созданного на шаге 1. Например, используйте имя сетевого сайта в Организации в качестве значения параметра NetworkSiteID1 и сетевой сайт ITSP в качестве значения параметра NetworkSiteID2. Дополнительные сведения приведены в статье [CREATE Network для межсайтовых политик в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) в документации по развертыванию. Кроме того, обратитесь к документации по командной консоли Lync Server для командлета New – CsNetworkInterSitePolicy.

3.  Получить IP-адрес точки завершения мультимедиа пограничного контроллера сеансов (SCB) у своего поставщика услуг Интернет-телефонии (ITSP). Добавить этот IP-адрес с маской подсети 32 к сетевому узлу, представляющему ITSP. Дополнительные сведения см. [в разделе Связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

</div>

<span> </span>

</div>

</div>

</div>

