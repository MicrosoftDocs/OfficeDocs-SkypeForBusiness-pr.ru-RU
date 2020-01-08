---
title: 'Lync Server 2013: Настройка сетевых сайтов для CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678cab0ea8b473e6ea33ab5db951b105a11fa78
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Настройка сетевых сайтов для CAC в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Если вы уже создали сайты сети для E9-1 или мультимедиа, вы можете изменить существующие сайты сети, чтобы применить профиль политики пропускной способности с помощью командлета <STRONG>Set-кснетворксите</STRONG> . Пример изменения сайта сети можно найти <A href="lync-server-2013-create-or-modify-a-network-site.md">в разделе Создание или изменение сайта сети в Lync Server 2013</A>.



</div>

*Сетевые сайты* — это офисы или места в каждом сетевом регионе управления допуском звонков (CAC), E9-1-1, а также с помощью мультимедийных развертываний. Для создания сайтов сети, которые выравниваются по сетевым сайтам в примере топологии сети для CAC, выполните указанные ниже действия. В этих процедурах показано, как создавать и настраивать сетевые сайты, ограниченные с помощью глобальной сети, и поэтому требуют политики пропускной способности, которые ограничивают поток аудио-или видеоканала в режиме реального времени.

В примере развертывания CAC для Северной Америки регион "Северная Америка" состоит из шести сайтов. На три из этих сайтов наложено пропускная способность глобальной сети: Рено, Портленде и Альбукерке. Другие три сайта, *не* ограниченные пропускной СПОСОБНОСТЬЮ глобальной сети: Нью-Йорк, Чикаго и Детройт. Пример создания или изменения этих сайтов сети можно найти [в разделе Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Пример топологии сети вы можете найти в статье [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

<div class=" ">


> [!NOTE]  
> В описанной ниже процедуре для создания сайта сети используется Командная консоль Lync Server Management Shell. Дополнительные сведения об использовании панели управления Lync Server для создания сайта можно найти в разделе <A href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сайта сети в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Создание сетевых сайтов для управления допуском звонков

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет **New-кснетворксите** для создания сайтов сети и применения к каждому сайту соответствующего профиля политики пропускной способности. Например, выполните командлет:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Чтобы завершить создание сайтов сети для всей топологии примера, повторите шаг 2 для сайтов сети с ограниченным доступом в регионах EMEA и APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

