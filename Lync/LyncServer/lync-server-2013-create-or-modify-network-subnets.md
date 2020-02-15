---
title: 'Lync Server 2013: создание или изменение сетевых подсетей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47075e96171bbeef5c2709e3eb38a480d08938f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Создание или изменение сетевых подсетей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Сеть должна быть сопоставлена с сетевым узлом для определения географического расположения узла, принадлежащего этой подсети. Для настройки подсетей можно использовать панель управления Lync Server. С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть. Более подробную информацию об удалении подсетей можно узнать в статье Удаление подсетей сети [в Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

В большинстве развертываний Microsoft Lync Server 2013, где реализован контроль допуска звонков (CAC), как правило, существует большое количество подсетей. Поэтому часто лучше настроить подсети из командной консоли Lync Server. Отсюда вы можете вызвать командлет **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV**. Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей. Примеры создания подсетей из файла CSV см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Создание подсети

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Network Configuration** (Параметры сети), а затем **Subnet** (Подсеть).

4.  На странице **Subnet** (Подсеть) нажмите кнопку **New** (Создать).

5.  Введите значение в поле **Subnet ID** (Идентификатор подсети) окна **New Subnet** (Новая подсеть). Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом из диапазона IP-адресов, определенного этой подсетью.

6.  В поле **Mask** (Маска) введите числовое значение от 1 до 32.
    
    <div>
    

    > [!NOTE]  
    > Это значение является битовой маской, применяемой к создаваемой подсети.

    
    </div>

7.  В области **Network site ID** (Идентификатор сетевого узла) выберите узел, к которому относится данная подсеть.

8.  (Необязательно) Введите значение в поле **Description** (Описание), чтобы предоставить дополнительную информацию о данной подсети, которую нельзя выразить одним только именем.

9.  Щелкните элемент **Commit** (Зафиксировать).

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Изменение подсети

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Network Configuration** (Параметры сети), а затем **Subnet** (Подсеть).

4.  На странице **Subnet** (Подсеть) щелкните подсеть, которую хотите изменить.

5.  В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).

6.  На странице **Edit Subnet** (Изменение подсети) вы можете изменить битовую маску, сопоставленную с сетевым узлом, или описание. При изменении битовой маски помните о том, что параметр идентификатора подсети должен оставаться первым адресом из диапазона IP-адресов, определенного этой подсетью.

7.  Щелкните элемент **Commit** (Зафиксировать).

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление сетевых подсетей в Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[Сведения о регионах сети, сайтах и подсетях в Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get — CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

