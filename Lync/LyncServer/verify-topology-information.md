---
title: Проверка сведений о топологии
description: Проверьте сведения о топологии.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed41cd95fffdca629e710dcf443631d0c74c69e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555495"
---
# <a name="verify-topology-information"></a>Проверка сведений о топологии

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

На первом этапе проверки успешного выполнения слияния необходимо просмотреть сведения о топологии Office Communications Server 2007 R2, Объединенные с Lync Server 2013. В построителе топологий узел **BackCompatSite** отображает полное доменное имя каждого пула Office Communications Server 2007 R2 и объединяемого сервера.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>Просмотр узла BackCompatSite в построителе топологий

1.  В среде Office Communications Server 2007 R2 откройте средство администрирования Office Communications Server 2007 R2 и запомните полные доменные имена устаревших пулов и серверов.

2.  В среде Lync Server 2013 откройте построитель топологий и разверните узел **BackCompatSite** .

3.  Проверьте, отображаются ли полные доменные имена объединяемых пулов и серверов.
    
    <div>
    

    > [!NOTE]  
    > В узле <STRONG>BackCompatSite</STRONG> не отображаются сведения о ролях серверов, размещаемых совместно на сервере переднего плана или сервере Standard Edition. Показаны только роли серверов, необходимые для взаимодействия между Office Communications Server 2007 R2 и Lync Server 2013.

    
    </div>

![Диалоговое окно "BackCompatSite" в построителе топологий](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Диалоговое окно "BackCompatSite" в построителе топологий")

Вы также можете использовать панель управления Lync Server 2013 для просмотра объединенной топологии. В панели управления Lync Server 2013 можно просмотреть полное доменное имя сервера, полное доменное имя пула и имя сайта для объединенной топологии. В поле **Сайт** для объединенных серверов указано имя **BackCompatSite**.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Просмотр объединенной топологии в панели управления Lync Server 2013

1.  Откройте панель управления Lync Server 2013.

2.  Щелкните пункт **Топология**.

3.  На вкладке **Состояние** проверьте, отображаются ли объединенные серверы и пулы, найдя серверы и пулы с именем **BackCompatSite** в столбце **Сайт**.

![Панель управления Lync Server, в которой отображается Объединенная топология](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Панель управления Lync Server, в которой отображается Объединенная топология")

Чтобы получить дополнительные сведения об объединенном пуле, воспользуйтесь командлетом **Get-CsPool**. В дополнение к сведениям, доступным в построителе топологий и панели управления Lync Server 2013, в этом командлете отображаются службы, которые выполняются в пуле Lync Server 2013.

<div>


> [!NOTE]  
> При публикации топологии после запуска мастера слияния в построителе топологий каталоги конференций объединяются в Lync Server 2013. Каталоги конференций можно проверить с помощью командлета <STRONG>Get-CsConferenceDirectory</STRONG>.



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>Просмотр служб в объединенном пуле

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду:
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Пример:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>Проверка объединения каталогов конференций

1.  Откройте консоль управления Lync Server 2013.

2.  Введите в командной строке следующую команду:
    
        Get-CsConferenceDirectory

3.  Убедитесь, что все каталоги конференций для пула или сервера, которые вы хотите объединить, теперь находятся в Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

