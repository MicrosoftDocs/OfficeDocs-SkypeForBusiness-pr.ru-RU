---
title: 'Lync Server 2013: настройка номеров доступа для конференц-связи с телефонным подключением'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2011-07-17_

При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.

Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами. Дополнительные сведения о регионах: [требования к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) в документации по планированию. Дополнительные сведения о настройке абонентской группы для конференц-связи с телефонным подключением можно найти в разделе Настройка абонентской [группы для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Вы не можете использовать новый номер доступа для телефонного подключения, пока не завершится репликация этого номера доступа в доменных службах Active Directory (AD&nbsp;DS). Репликация может занять несколько часов.



</div>

<div>


> [!NOTE]  
> Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа. Используйте командлет <STRONG>Set-ксдиалинконференЦингакцесснумбер</STRONG> , чтобы изменить отображаемое имя. Не следует изменять объекты Active Directory вручную. Дополнительные сведения об изменении номера для доступа можно найти в документации по командной консоли Lync Server Management Shell для командлета <STRONG>Set-ксдиалинконференЦингакцесснумбер</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>Содержание

[Создание или изменение номера доступа к конференции с телефонным подключением в Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

