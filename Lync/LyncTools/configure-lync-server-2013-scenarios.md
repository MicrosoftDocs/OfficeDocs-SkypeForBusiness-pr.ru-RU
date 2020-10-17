---
title: Настройка сценариев Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499946"
---
# <a name="configure-lync-server-2013-scenarios"></a>Настройка сценариев Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-12-28_

Для запуска средства нагрузки и производительности Lync Server 2013 (Линкперфтул) сначала необходимо настроить топологию Lync Server 2013, чтобы выполнить сценарии, которые будут выполняться. Если Lync Server 2013 не настроен или настроен неправильно, в большинстве случаев произойдет ошибка моделирования нагрузки. С помощью средства нагрузки и производительности Lync Server 2013 мы предоставили примеры сценариев командной консоли Lync Server и базовых файлов ресурсов, которые можно использовать в качестве отправной точки для настройки Lync Server 2013. В этом разделе описываются приведенные примеры Windows PowerShell. Обратите внимание, что в этом разделе нет цели, описывающих, как настроить Lync Server 2013 в целом. Подробные сведения о работе с Windows PowerShell в Lync Server 2013 можно найти в документации по консоли управления Lync Server по адресу <https://technet.microsoft.com/library/gg398474.aspx> :.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Сведения о выполнении сценариев командной консоли Lync Server

Мы предоставили примеры сценариев командной консоли Lync Server, которые можно использовать при подготовке к запуску нагрузочного моделирования. Так как сценарии предназначены для имитации нагрузки, они просты и отличаются, поэтому могут быть не подходящими для рабочей среды. Все скрипты являются примерами и должны быть просмотрены, а в некоторых случаях изменены в соответствии с топологией. Как минимум, ожидается, что сценарий службы группы ответа (RGS) потребуется изменить, чтобы указать агенты, назначенные группам агентов. Тем не менее, вы можете не имитировать эту нагрузку.

<div>


> [!WARNING]  
> Будьте внимательны и ознакомьтесь с представленными примерами. Сценарии заменят все существующие параметры в топологии.



</div>

<div>


> [!NOTE]  
> Для получения дополнительных сведений об использовании Windows PowerShell и командной консоли Lync Server обратитесь к блогу Lync Server 2013 Windows PowerShell по адресу <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Специальные имена клиента средства нагрузки и производительности

Если вы изменили параметры из значений по умолчанию, может потребоваться настроить политику проверки версий клиентов. Дополнительные сведения см. в разделе "Настройка поддерживаемых версий клиентов" <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> . При обмене данными с Lync Server 2013 средство нагрузки и производительности Lync Server 2013 по умолчанию использует следующие версии агента пользователя:

  - ЛСПТ/15.0.0.0 (средство тестирования нагрузки и производительности Lync Server 2013)

  - ОКФОНЕ/. 0.522

Они предназначены для клиента Mobility (UCWA) в Линкперфтул:

  - Средство производительности Ucwa/веб-конференция

  - Ucwa Perf Tool/Mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>

