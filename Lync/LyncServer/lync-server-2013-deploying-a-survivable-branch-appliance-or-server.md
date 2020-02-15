---
title: 'Lync Server 2013: развертывание устройства или сервера для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445df692041e24f8a4e134836ea9f6a63561a2ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-12-10_

Отказоустойчивая Корпоративная голосовая связь относится к устойчивости сайта филиала, то есть возможность предоставлять непрерывную службу голосовой связи пользователям сайта филиала в случае, если ссылка на центральный сайт становится недоступна.

Для небольших и средних сайтов филиалов (сайты филиалов с 25 до 1 000 пользователей) рекомендуется развернуть устройство для обеспечения связи в филиалах, которое будет завершать вызовы по телефонной сети общего пользования с помощью встроенного шлюза PSTN или магистральной линии SIP для телефонного подключения поставщик услуг. Устройство для обеспечения связи в филиалах — это стороннее устройство, включающее в себя блейд-сервер, на котором работает операционная система Windows Server 2008 R2, регистратор Lync Server 2013, программное обеспечение сервера-посредника и шлюз PSTN, все в корпусах с одним устройством.

Для сайтов филиалов с 1 000 до 5 000 и без отказоустойчивой глобальной сети рекомендуется подключить к поставщику телефонной связи сервер для обеспечения связи в филиалах с шлюзом PSTN или магистральной магистралью SIP. Сервер для обеспечения связи в филиалах — это компьютер с Windows Server, на котором установлено программное обеспечение регистратора и сервер-посредник.

<div>


> [!NOTE]  
> Для сайтов филиалов с более чем 5 000 пользователями и выделенными администраторами Lync Server рекомендуется использовать полное развертывание Lync Server 2013, отделенное от центрального сайта.<BR>Дополнительные сведения о выборе оптимального решения устойчивости для сайтов филиалов в Организации, в том числе необходимых условий и рекомендаций по планированию, приведены в разделе <A href="lync-server-2013-branch-site-resiliency-requirements.md">требования к устойчивости сайтов филиалов для Lync Server 2013</A> в документации по планированию.



</div>

<div>


> [!NOTE]  
> Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Настройка пользователей для обеспечения устойчивости сайта филиала в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Домашние пользователи на устройстве или сервере для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Приложения: устройства и серверы для обеспечения связи в филиалах в Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

