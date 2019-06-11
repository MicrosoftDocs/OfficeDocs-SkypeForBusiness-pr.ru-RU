---
title: 'Lync Server 2013: Настройка регионов сети для CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Настройка регионов сети для CAC в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Если вы уже создали регионы сети для E9-1 или мультимедиа, вы можете изменить существующие сетевые регионы, добавив параметры, специфические для управления допуском звонков (CAC), с помощью командлета <STRONG>Set-кснетворкрегион</STRONG> . Пример, посвященный изменению сетевого региона, можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в разделе Создание или изменение сетевого региона в Lync Server 2013</A>.



</div>

*Регионы сетей* — это сетевые разветвители и одинарные кости, которые используются при настройке CAC, E9-1-1 и мультимедийного обхода. Используйте описанную ниже процедуру для создания областей сети, которые выравниваются по сетевым областям в примере использования CAC в топологии сети. Пример топологии сети вы можете найти в статье [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

Пример топологии сети для CAC состоит из трех регионов: Северная Америка, EMEA и APAC. Каждый регион имеет указанный центральный сайт. Для региона Северной Америки указанный центральный сайт называется Чикаго. Ниже приведен пример использования командлета **New-кснетворкрегион** для создания области для Северной Америки.

<div>


> [!NOTE]  
> В описанной ниже процедуре для создания сетевого региона используется Командная консоль Lync Server Management Shell. Дополнительные сведения об использовании панели управления Lync Server для создания сетевого региона можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в разделе Создание или изменение сетевого региона в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Создание сетевого региона для управления допуском звонков

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Для каждого региона, который необходимо создать, выполните командлет **New-кснетворкрегион** . Например, чтобы создать регион для Северной Америки, выполните следующие действия:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Повторите шаг 2, чтобы создать сетевые регионы, EMEA и APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

