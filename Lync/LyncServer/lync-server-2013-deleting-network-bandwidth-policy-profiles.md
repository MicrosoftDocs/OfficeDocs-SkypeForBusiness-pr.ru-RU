---
title: 'Lync Server 2013: удаление профилей политики пропускной способности сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c33f781e8818dbefa3dc37b3f17c789099e6add
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Удаление профилей политики пропускной способности сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности. В Microsoft Lync Server 2013 можно назначать ограничения пропускной способности только для модальностей аудио и видео. Вы можете настроить общие ограничения пропускной способности и ограничения сеанса. С помощью панели управления Lync Server вы можете создавать, изменять и удалять профили контейнеров для этих политик. Для удаления профилей политики пропускной способности сети выполните указанные ниже действия. Подробнее о создании или изменении профиля политики пропускной способности сети можно узнать [в разделе Создание и изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Удаление профиля политики пропускной способности

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **политика пропускной способности**.

4.  На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите удалить.
    
    <div>
    

    > [!NOTE]  
    > За один раз можно удалить сразу несколько профилей. Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, выберите несколько профилей. Кроме того, чтобы выбрать все профили, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.
    
    <div>
    

    > [!WARNING]  
    > Вы не можете удалить профиль политики пропускной способности, связанный с сетевым сайтом. Прежде чем удалять профиль, необходимо сначала удалить связь с сетевым сайтом. Сведения о том, как изменить сетевой сайт, можно найти <A href="lync-server-2013-creating-or-modifying-network-sites.md">в разделе Создание и изменение сетевых сайтов в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание и изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Просмотр данных профиля политики пропускной способности сети в Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Настройка управления допуском звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

