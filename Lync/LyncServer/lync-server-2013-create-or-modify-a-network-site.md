---
title: 'Lync Server 2013: создание или изменение сетевого сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Создание или изменение сетевого сайта в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-24_

Управление допуском звонков (CAC), E9-1-1, а для обхода мультимедийных развертываний используются *Сетевые сайты* , определенные внутри и всегда связанные с сетевым регионом. Сетевой сайт представляет местонахождение офиса подразделения, набор зданий или кампус. Сетевые сайты представляют собой коллекции подсетей с одинаковой пропускной способностью.

Чтобы создать или изменить сетевые сайты, выполните указанные ниже действия. Например, если вы уже создали сетевые сайты для одной голосовой связи, вам не нужно создавать новые сетевые сайты; другие функции голосовой связи будут использовать те же сайты. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.

<div>


> [!NOTE]  
> Там, где они есть, вы можете найти конкретные примеры и требования к сетевым сайтам, которые относятся к дополнительным функциям голосовой связи в документации по развертыванию для каждой из функций. 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Настройка сетевых сайтов для CAC в Lync Server 2013</A></P></LI></UL>



</div>

Дополнительные сведения о работе с сетевыми сайтами можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Создание сайта сети

Создание сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Создание сетевого сайта с помощью командной консоли

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Выполните командлет New-CsNetworkSite для создания областей сети:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Например:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    В этом примере создается сетевой узел с именем "Chicago" в области сети "NorthAmerica".
    
    <div>
    

    > [!NOTE]  
    > Чтобы эта команда выполнилась успешно, область сети NorthAmerica должна уже быть создана.

    
    </div>

3.  Чтобы закончить создание сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Создание сайта сети с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Нажмите кнопку навигации **Сайт**.

4.  Выберите **Создать**.

5.  На странице **Создать сайт** выберите поле **Имя** и введите имя для сетевого сайта.

6.  Нажмите пункт **Область** и выберите в списке нужную область.

7.  Дополнительно можно выбрать пункт **Политика пропускной способности** и выбрать нужную политику в списке.
    
    <div>
    

    > [!NOTE]  
    > Политика пропускной способности требуется только в том случае, если в узле разворачивается контроль допуска звонков.

    
    </div>

8.  Дополнительно можно выбрать пункт **Политика местонахождения** и выбрать нужную политику местонахождения в списке.
    
    <div>
    

    > [!NOTE]  
    > Политика местонахождения требуется только в том случае, если в узле разворачивается служба E9-1-1.

    
    </div>

9.  В поле **Описание** введите дополнительные сведения об области сети (необязательно).

10. Нажмите **Исполнить**.

11. Чтобы завершить создание сетевых узлов для вашей топологии, повторите действия с 4 по 10 с параметрами для других узлов.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Изменение сетевого сайта

Изменение сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.

<div>

## <a name="to-modify-a-network-site"></a>Изменение сетевого сайта

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы изменить сетевые узлы, выполните командлет Set-CsNetworkSite:
    
        Set-CsNetworkSite -Identity <string>
    
    Например:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    В данном примере узел с именем "Albuquerque" перемещается в область сети "NorthAmerica". Чтобы изменить конфигурацию этого сетевого узла для развертывания контроля допуска звонков, E9-1-1 или обхода сервера-посредника, измените параметры сетевого узла, выполнив командлет Set-CsNetworkSite с параметром BWPolicyProfileID или LocationPolicy соответственно.
    
    <div>
    

    > [!NOTE]  
    > Хотя для обхода сервера-посредника существует параметр BypassID, настоятельно рекомендуется не переопределять автоматически созданные идентификаторы обхода. Чтобы настроить сетевой узел для обхода сервера-посредника, указывать дополнительные параметры не требуется.

    
    </div>

3.  Чтобы закончить изменение сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Изменение сетевого сайта с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Нажмите кнопку навигации **Сайт**.

4.  Выберите в таблице сетевой узел, который требуется изменить.

5.  Щелкните **Изменить**, затем щелкните **Подробнее**.

6.  На странице **Изменение сайта** соответствующим образом измените значения параметров для этого сетевого узла.

7.  Нажмите **Исполнить**.

8.  Чтобы завершить изменение сетевых узлов, повторите действия с 4 по 7 с параметрами для других узлов.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

