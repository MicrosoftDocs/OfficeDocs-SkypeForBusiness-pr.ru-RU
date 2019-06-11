---
title: 'Lync Server 2013: создание политик межсайтовой сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Создание политик межсайтовой сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

*Политика* межсетевое соединение определяет ограничения пропускной способности между сайтами, которые имеют прямые WAN-ссылки между ними.

Дополнительные сведения можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Политика межсетевого сайта требуется <EM>только</EM> в том случае, если имеется прямая перекрестная связь между двумя сетевыми сайтами.



</div>

В примере в Северной Америке для топологии есть прямая связь между сайтами Рено и Альбукерке. Для этих двух сайтов требуется межсайтовая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере используется профиль ссылки\_20Mb.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Создание политики межсетевого соединения

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запустите командлет New-Кснетворкинтерситеполици, чтобы создать политики межсетевого сайта и применить соответствующий профиль политики пропускной способности для двух сайтов с прямой перекрестной связью. Например, выполните командлет:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  При необходимости повторите шаг 2, чтобы создать политики межсетевого сайта для всех пар сетевых сайтов, имеющих прямую перекрестную ссылку.

</div>

</div>

<span> </span>

</div>

</div>

</div>

