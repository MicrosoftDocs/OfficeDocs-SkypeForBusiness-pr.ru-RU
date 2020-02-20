---
title: 'Lync Server 2013: Настройка областей сети для контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0b79ade468300928edded9830219ba06b11b4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Настройка сетевых регионов для CAC в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Если области сети для E9-1-1 или обхода сервера-посредника уже созданы, измените эти существующие области, добавив параметры, относящиеся к контролю допуска звонков, с помощью командлета <STRONG>Set-CsNetworkRegion</STRONG>. Пример, посвященный изменению области сети, представлен <A href="lync-server-2013-create-or-modify-a-network-region.md">в статье Создание или изменение области сети в Lync Server 2013</A>.



</div>

*Области сети* — это сетевые концентраторы или магистрали, используемые в конфигурациях контроля допуска звонков, E9-1-1 и обхода сервера-посредника. Используйте следующие процедуры для создания областей сети, которые совмещаются с областями сети в примере топологии сети для контроля допуска звонков. Пример сетевой топологии представлен в статье [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

В этом примере топологии сети для контроля допуска звонков имеется три области: North America (Северная Америка), EMEA (Европа, Ближний Восток и Африка) и APAC (азиатско-тихоокеанский регион). Каждая область имеет свой центральный сайт. Для области Северной Америки (NorthAmerica) назначенный центральный сайт называется CHICAGO. В следующей процедуре показано, как можно создать область NorthAmerica с помощью командлета **New-CsNetworkRegion**.

<div>


> [!NOTE]  
> В следующей процедуре для создания области сети используется Командная консоль Lync Server. Дополнительные сведения о создании области сети с помощью панели управления Lync Server можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в статье Создание или изменение области сети в Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Создание области сети для контроля допуска звонков

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните командлет **New-CsNetworkRegion** для каждой области, которую требуется создать. Например, чтобы создать область NorthAmerica, выполните следующую команду:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Повторите действие 2 для создания областей сети EMEA и APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

