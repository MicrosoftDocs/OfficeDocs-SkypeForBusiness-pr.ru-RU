---
title: Проверка сведений о топологии
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7657bb80d7acb6d48a4027c665fae70e469bb236
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>Проверка сведений о топологии

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-26_

Первый этап проверки успешности слияния — Просмотр сведений о топологии Office Communications Server 2007 R2, которые вы объединили с помощью Lync Server 2013. В построителе топологии в узле **бакккомпатсите** отображается полное доменное имя (FQDN) для каждого пула и сервера Office Communications Server 2007 R2, который вы объединили.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Просмотр Бакккомпатсите в построителе топологии

1.  В среде Office Communications Server 2007 R2 откройте средство администрирования Office Communications Server 2007 R2 и запомните полные доменные имена старых пулов и серверов.

2.  В среде Lync Server 2013 откройте "Построитель топологии", а затем разверните узел **бакккомпатсите** .

3.  Убедитесь в том, что полные доменные имена для объединяемых пулов и серверов отображены.
    
    <div>
    

    > [!NOTE]  
    > В <STRONG>бакккомпатсите</STRONG> не отображаются никакие данные для ролей сервера, размещенных на сервере переднего плана или стандартном сервере Standard Edition. Показаны только роли сервера, необходимые для взаимодействия между Office Communications Server 2007 R2 и Lync Server 2013.

    
    </div>

![Диалоговое окно "Бакккомпатсите Topology Builder"] (images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Диалоговое окно \"Бакккомпатсите Topology Builder\"")

Вы также можете использовать панель управления Lync Server 2013, чтобы просмотреть объединенную топологию. В панели управления Lync Server 2013 вы можете просмотреть полные доменные имена серверов, FQDN и имя пула для объединенной топологии. У Объединенных серверов есть имя **сайта** **бакккомпатсите**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Просмотр объединенной топологии в Lync Server 2013 панели управления

1.  Откройте панель управления Lync Server 2013.

2.  Нажмите **топология**.

3.  На вкладке **Status (состояние** ) убедитесь в том, что Объединенные серверы и пулы отображаются по столбцу " **сайт** ", выполнив поиск **бакккомпатсите** .

![Объединенная топология на панели управления сервера Lync Server] (images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Объединенная топология на панели управления сервера Lync Server")

Чтобы просмотреть дополнительные сведения о объединенном пуле, используйте командлет **Get-кспул** . В дополнение к сведениям, доступным в построителе топологии и панели управления Lync Server 2013, в этом командлете выводятся службы, которые выполняются в пуле Lync Server 2013.

<div>


> [!NOTE]  
> После публикации топологии после запуска мастера слияния в построителе топологии каталоги конференций объединяются в Lync Server 2013. Каталоги конференций можно проверить, запустив командлет <STRONG>Get-ксконференцедиректори</STRONG> .



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Просмотр служб в Объединенном пуле

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Например:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Проверка Объединенных каталогов конференций

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду:
    
        Get-CsConferenceDirectory

3.  Убедитесь в том, что все каталоги конференций для пула или сервера, который вы собираетесь объединять, теперь находятся в Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

