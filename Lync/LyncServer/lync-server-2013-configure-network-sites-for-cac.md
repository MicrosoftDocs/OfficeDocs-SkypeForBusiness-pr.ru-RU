---
title: 'Lync Server 2013: Настройка сетевых сайтов для контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Если вы уже создали сетевые сайты для службы E9-1-1 или обхода сервера-посредника, то вы можете применить к ним профиль политики пропускной способности с помощью командлета <STRONG>Set-CsNetworkSite</STRONG>. Пример изменения сетевого сайта представлен <A href="lync-server-2013-create-or-modify-a-network-site.md">в статье Создание или изменение сетевого сайта в Lync Server 2013</A>.



</div>

*Сетевые сайты* — это офисы или расположения в каждой области сети контроля допуска звонков, E9-1-1 и обхода сервера-посредника. Чтобы создать сетевые сайты, соответствующие примеру топологии сети для контроля допуска звонков, используйте следующие процедуры. В этих процедурах демонстрируется создание и настройка сетевых сайтов, на которые распространяется ограничение пропускной способности глобальной сети. Следовательно, для этих сетевых сайтов требуются политики пропускной способности, которые ограничивают трафик звуковых и видеоданных в режиме реального времени.

В примере развертывания контроля допуска звонков регион Северная Америка содержит 6 сайтов. На 3 сайта распространяется ограничение пропускной способности глобальной сети: Рино, Портленд и Альбукерке. На оставшиеся 3 сайта ограничение пропускной способности глобальной сети *не* действует: Нью-Йорк, Чикаго и Детройт. Пример создания или изменения этих других сетевых сайтов представлен [в статье Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Пример сетевой топологии представлен в статье [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

<div class=" ">


> [!NOTE]  
> В следующей процедуре для создания сетевого сайта используется Командная консоль Lync Server. Дополнительные сведения об использовании панели управления Lync Server для создания сетевого сайта можно узнать <A href="lync-server-2013-create-or-modify-a-network-site.md">в статье Создание или изменение сетевого сайта в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Создание сетевых узлов для контроля допуска звонков

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать сетевые сайты и применить требуемый профиль политики пропускной способности для каждого сайта, выполните командлет **New-CsNetworkSite**. Пример:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Чтобы завершить создание сетевых сайтов для всего примера топологии, повторите шаг 2 для сетевых сайтов с ограничением пропускной способности, расположенных в Европе, на Ближнем Востоке и в Африке, а также в Азиатско-тихоокеанском регионе.

</div>

</div>

<span> </span>

</div>

</div>

</div>

