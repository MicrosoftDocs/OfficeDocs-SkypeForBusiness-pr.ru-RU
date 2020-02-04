---
title: 'Lync Server 2013: развертывание устройства или сервера обеспечения связи в филиалах'
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
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Развертывание устройства или сервера обеспечения связи в филиалах с Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-12-10_

Отказоустойчивая Корпоративная голосовая связь — это возможность предоставления постоянной корпоративной голосовой связи пользователям сайтов филиалов в случае, если ссылка на центральный сайт станет недоступна.

Для небольших и средних сайтов филиалов (сайтов филиалов с 25 до 1 000 пользователей) рекомендуется развертывание бесперебойно работающего устройства филиалов, который будет прерывать вызовы по коммутируемой телефонной сети с помощью встроенного шлюза PSTN или канала SIP на телефон. поставщик услуг. Бесперебойно работающее приложение-ветвь — это стороннее устройство, включающее в себя сервер с операционной системой Windows Server 2008 R2, регистратор Lync Server 2013, программное обеспечение сервера-посредников и шлюз PSTN в одном корпусе устройства.

Для сайтов филиалов с 1 000 до 5 000 и без гибкой глобальной сети рекомендуется подключить одноадресный сервер к поставщику услуг телефонной связи либо к шлюзу PSTN, либо к магистрали SIP. Бесперебойный сервер подразделения — это компьютер под управлением Windows, на котором установлено программное обеспечение регистратора и сервер-посредника.

<div>


> [!NOTE]  
> Для сайтов филиалов, в которых более 5 000 пользователей и выделенные администраторы сервера Lync Server, рекомендуется использовать полное развертывание Lync Server 2013, отделенное от центрального сайта.<BR>Подробные сведения о выборе наилучшего решения для обеспечения устойчивости для сайтов филиалов в Организации, в том числе о предварительных требованиях и планировании, приведены в разделе <A href="lync-server-2013-branch-site-resiliency-requirements.md">требования к устойчивости сайтов для Lync Server 2013</A> в документации по планированию.



</div>

<div>


> [!NOTE]  
> Пользователи, расположенные на устройстве с бесперебойной подразделением Lync Server, не могут создавать новые комнаты чата и просматривать открытку для существующих комнат.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задачи центрального сайта](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Настройка пользователей для организации устойчивости на сайтах филиалов в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Пользователи, работающие дома на устройстве или сервере для обеспечения связи в филиалах, в Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

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

