---
title: 'Lync Server 2013: создание связей между областями сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af9c2d6b651fd127986d89d521e99745e1af384
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>Создание связей между областями сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Регионы в сети связываются с помощью физического подключения глобальной сети. *Связь между областями сети* создает канал между двумя областями, настроенными для контроля допуска звонков (CAC), и задает ограничения пропускной способности трафика аудио- и видеоданных между этими областями.

Для получения подробных сведений о работе с ссылками на область сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove — Кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

Пример топологии содержит ссылку между регионами "Северная Америка" и "APAC" и ссылку между регионами "EMEA" и "APAC". Каждая из этих связей между регионами ограничена пропускной способностью WAN, как описано в таблице сведения о пропускной способности канала связи в [примере: сбор требований для контроля допуска звонков в разделе Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>Создание связей между областями с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>Создание связей между областями с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Нажмите кнопку навигации **Region Link** (Связь между областями).

4.  Нажмите кнопку **Создать**.

5.  На странице **New Region Link** (Создание связи между областями) щелкните поле **Имя** и введите имя для связи между областями сети.

6.  Щелкните **область \#сети 1**, а затем выберите в списке область сети, которую требуется связать с областью \#сети 2.

7.  Щелкните **область \#сети 2**, а затем выберите регион сети в списке, который необходимо связать с областью \#сети 1.

8.  Кроме того, можно щелкнуть элемент **Bandwidth policy** (Политика пропускной способности), а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.
    
    <div class=" ">
    

    > [!NOTE]  
    > Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу.

    
    </div>

9.  Нажмите кнопку **Зафиксировать**.

10. Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.

</div>

</div>

<span> </span>

</div>

</div>

</div>
