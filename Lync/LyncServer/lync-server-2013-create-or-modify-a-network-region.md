---
title: 'Lync Server 2013: создание или изменение сетевого региона'
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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Создание или изменение сетевого региона в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

*Регионы сетей* — это сетевые разветвители и одинарные кости, используемые в настройке управления допуском звонков, E9-1-1 и мультимедийными пропусками. Для создания и изменения областей сети выполните указанные ниже действия. Например, если вы уже создали сетевые регионы для одной голосовой связи, вам не нужно создавать новые сетевые регионы; другие дополнительные функции для корпоративной голосовой связи будут использовать те же сетевые регионы. Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции. Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт. Подробности можно найти [в разделе Настройка регионов сети для CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Любые особые требования к функциональным возможностям для определений сетевых областей описаны в разделе Развертывание для этой функции.



</div>

Дополнительные сведения о работе с сетевыми областями можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Создание сетевого региона

Создание сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Создание сетевого региона с помощью командной консоли Lync Server Management Shell

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы создать области сети, используйте командлет New-CsNetworkRegion.
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Например:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    В этом примере показано создание области сети "NorthAmerica", которая связана с центральным сайтом с ИД CHICAGO.

3.  Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Создание сетевого региона с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Щелкните **Область**.

4.  Выберите **Создать**.

5.  На странице **Создание области** введите имя области сети в поле **Имя**.

6.  Щелкните **Центральный сайт**, затем выберите центральный сайт в списке.

7.  В поле **Описание** введите дополнительные сведения об области сети (необязательно).

8.  Нажмите **Исполнить**.

9.  Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Изменение сетевого региона

Измените параметры существующего сетевого региона, чтобы внести изменения в основные сведения о регионе или изменения, необходимые для новой функции.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Изменение сетевого региона с помощью командной консоли Lync Server Management Shell

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Например:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    В этом примере показано изменение описания области сети "NorthAmerica", созданной ранее. Если для области "NorthAmerica" описание уже задано, оно будет перезаписано; в противном случае описание будет задано.

3.  Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Изменение сетевого региона с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните элемент **Конфигурация сети**.

3.  Нажмите кнопку навигации **Область**.

4.  В таблице щелкните область сети, которую требуется изменить.

5.  Щелкните **Изменить**, затем щелкните **Подробнее**.

6.  На странице **Изменение области** измените требуемые параметры области сети.

7.  Нажмите **Исполнить**.

8.  Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

