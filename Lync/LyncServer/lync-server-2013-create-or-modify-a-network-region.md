---
title: 'Lync Server 2013: создание или изменение области сети'
description: 'Lync Server 2013: создание или изменение области сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a149a668f64df804d2631243d9bb63401bd8a284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562235"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Создание или изменение области сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

*Области сети* представляют сетевые концентраторы или магистрали, используемые при настройке контроля допуска звонков, службы E9-1-1 и обхода сервера-посредника. Для создания и изменения областей сети используйте процедуры, описанные в этом разделе. Например, если вы уже создали области сети для одной функции голосовой связи, то вам не потребуется создавать новые области сети, поскольку остальные функции корпоративной голосовой связи будут использовать имеющиеся области сети. Тем не менее, возможно, потребуется изменить существующее определение области сети, чтобы применить специальные настройки для конкретных компонентов. Например, когда после создания областей сети для системы E9-1-1 (которой не требуется связанный центральный сайт) выполняется развертывание системы контроля допуска звонков, потребуется изменить определения области сети для указания центрального сайта. Дополнительные сведения см. [в статье configure Network regions for CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Все специальные требования в отношении определений области сети для конкретных компонентов указаны в документации по развертыванию данных компонентов.



</div>

Для получения подробных сведений о работе с областями сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [New — CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get — CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set — CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove — CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Создание области сети

Создание области сети, которая может использоваться службой контроля допуска звонков, службой E9-1-1 или при обходе сервера-посредника.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Создание области сети с помощью консоли управления Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать области сети, используйте командлет New-CsNetworkRegion.
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Пример:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    В этом примере показано создание области сети "NorthAmerica", которая связана с центральным сайтом с ИД CHICAGO.

3.  Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Создание области сети с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Щелкните **Region** (Область).

4.  Щелкните **New** (Создать).

5.  На странице **New Region** (Создание области) введите имя области сети в поле **Name** (Имя).

6.  Щелкните **Central site** (Центральный сайт) и затем выберите центральный сайт в списке.

7.  В поле **Description** (Описание) введите дополнительные сведения об области сети (необязательно).

8.  Щелкните **Commit** (Применить).

9.  Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Изменение области сети

Изменение параметров существующей области сети в соответствии с изменениями основных сведений об области сети или требованиями новой функции.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Изменение области сети с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Пример:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    В этом примере показано изменение описания области сети "NorthAmerica", созданной ранее. Если для области "NorthAmerica" описание уже задано, оно будет перезаписано; в противном случае описание будет задано.

3.  Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Изменение области сети с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Нажмите кнопку навигации **Region** (Область).

4.  В таблице щелкните область сети, которую требуется изменить.

5.  Щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).

6.  На странице **Edit Region** (Изменение области) измените требуемые параметры области сети.

7.  Щелкните **Commit** (Применить).

8.  Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

