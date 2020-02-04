---
title: 'Lync Server 2013: создание и изменение подсетей сети'
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
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Создание и изменение подсетей сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Сетевая подсеть должна быть связана с сетевым сайтом в целях определения географического расположения узла, принадлежащего данной подсети. Вы можете настроить подсети с помощью панели управления Lync Server. С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые подсети. Подробнее об удалении подсетей сети можно узнать в разделе Удаление подсетей сети [в Lync Server 2013](lync-server-2013-deleting-network-subnets.md).

В большинстве развертываний Microsoft Lync Server 2013 там, где реализовано управление допуском звонков (CAC), обычно это большое количество подсетей. По этой причине лучше всего настроить подсети из командной консоли Lync Server Management Shell. Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**. Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей. Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-create-a-network-subnet"></a>Создание сетевой подсети

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.

4.  На странице " **подсеть** " нажмите кнопку " **создать**".

5.  В разделе **Новая подсеть**введите значение в поле **код подсети** . Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом в диапазоне IP-адресов, определенном подсетью.

6.  В поле " **Маска** " введите числовое значение от 1 до 32.
    
    <div>
    

    > [!NOTE]  
    > Это значение — битовая маска, применяемая к создаваемой подсети.

    
    </div>

7.  В поле " **код сайта сети**" выберите сайт, к которому относится эта подсеть.

8.  Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения о подсети, которые нельзя выразить только именем.

9.  Нажмите **Исполнить**.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>Изменение подсети сети

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.

4.  На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите изменить.

5.  В меню **Правка** щелкните **Подробнее**.

6.  На странице **Изменение подсети** вы можете изменить битовую маску, связанный сетевой сайт или описание. Если вы измените битовую маску, имейте в виду, что идентификатор подсети по-прежнему должен быть первым в диапазоне IP-адресов, определенном подсетью.

7.  Нажмите **Исполнить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление подсетей сети в Lync Server 2013](lync-server-2013-deleting-network-subnets.md)  


[О сетевых областях, сайтах и подсетях в Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

