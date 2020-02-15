---
title: 'Lync Server 2013: Настройка номеров доступа к конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4762971397192dc45fdcc402d40c2adec72414f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2011-07-17_

При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.

Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами. Сведения о регионах можно найти в статье Планирование [конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) в документации по планированию. Дополнительные сведения о настройке абонентских группы для конференц-связи с телефонным подключением приведены [в статье Настройка абонентских группы для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Вы не можете использовать новый номер доступа для телефонного подключения, пока не завершится репликация этого номера доступа в доменных службах Active Directory (AD&nbsp;DS). Репликация может занять несколько часов.



</div>

<div>


> [!NOTE]  
> Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа. Чтобы изменить отображаемое имя, используйте командлет <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>. Объекты Active Directory не следует изменять вручную. Для получения дополнительных сведений об изменении номера доступа, обратитесь к документации по командной консоли Lync Server для командлета <STRONG>Set – CsDialInConferencingAccessNumber</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>Содержание

[Создание или изменение номера доступа к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

