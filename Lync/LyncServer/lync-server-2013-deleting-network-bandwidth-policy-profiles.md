---
title: 'Lync Server 2013: удаление профилей политики пропускной способности сети'
description: 'Lync Server 2013: удаление профилей политики пропускной способности сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552665"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Удаление профилей политики пропускной способности сети в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей. В Microsoft Lync Server 2013 ограничения пропускной способности могут быть назначены только для модальности аудио и видео. Вы можете задать общие ограничения и ограничения сеанса. Вы можете использовать панель управления Lync Server для создания, изменения или удаления профиля контейнера для этих политик. Используйте следующие процедуры для удаления профилей политик пропускной способности сети. Подробнее о создании или изменении профиля политики пропускной способности сети можно узнать [в статье Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Чтобы удалить профиль политики пропускной способности

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика пропускной способности**.

4.  На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который следует удалить.
    
    <div>
    

    > [!NOTE]  
    > Одновременно можно удалить сразу несколько профилей. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько профилей. Или щелкните пункт <STRONG>Выделить все</STRONG> в меню <STRONG>Изменить</STRONG> для выбора сразу нескольких профилей.

    
    </div>

5.  В меню **Изменить** щелкните **Удалить**.
    
    <div>
    

    > [!WARNING]  
    > Невозможно удалить профили политики пропускной способности, связанные с сетевым сайтом. Сначала следует удалить связь с сетевым сайтом, а затем удалить профиль. Сведения о том, как изменить сетевой сайт, можно найти <A href="lync-server-2013-creating-or-modifying-network-sites.md">в статье Создание или изменение сетевых сайтов в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Просмотр сведений о профиле политики пропускной способности сети в Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Настройка контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove — CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

