---
title: 'Lync Server 2013: планирование конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b7813a197dd7cc3116540c605d7efbdb22a04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Планирование конференц-связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-29_

Lync Server 2013 имеет широкий набор возможностей для конференц-связи:

  - Веб-конференции, в том числе взаимодействие с документами, общий доступ к приложениям и совместный доступ к рабочему столу. Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint. Подробнее об установке и настройке сервера Office Web Apps можно узнать в разделе [Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Голосовая или видеосвязь (A/V), позволяющая пользователям использовать голосовые и видеоконференции в реальном времени, не требуя использования внешних служб, таких как служба Microsoft Live Meeting или независимый звуковой мост.

  - Конференц-связь с телефонным подключением, благодаря которой пользователи могут присоединиться к звуковой части конференции Lync Server 2013 с помощью коммутируемого телефона с коммутируемой телефонной сетью, не требуя от стороннего поставщика услуг голосовой связи.

  - Конференц-связь с помощью мгновенных сообщений, в которой более двух сторон обмениваются данными в одном сеансе обмена мгновенными сообщениями. Подробные сведения о конференц-связи можно найти [в разделе Планирование серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 поддерживает как запланированные конференции, так и конференции незапланированное.

При развертывании Lync Server 2013, сервер переднего плана вы можете выбрать, следует ли также развертывать веб-конференции, Конференции и возможности конференц-связи с телефонным подключением. Возможности конференц-связи с СООБЩЕНИЯми всегда развертываются автоматически вместе с возможностями обмена мгновенными сообщениями на серверах переднего плана Lync Server 2013.

<div>


> [!NOTE]  
> Если в развертывании есть собрания, упорядоченные с помощью клиентов Office Communicator 2007 R2 (включая консоль Live Meeting или надстройка конференц-связи для Microsoft Office Outlook), после миграции в Lync эти собрания будут иметь указанные ниже ограничения. Сервер 2013: 
> <UL>
> <LI>
> <P>Пользователи на собрании не смогут использовать возможности совместной работы с данными, в том числе совместную работу с документами, общий доступ к приложениям и совместный доступ к рабочему столу.</P>
> <LI>
> <P>Проблемы с стабильностью могут возникать, так как клиенты Office Communicator 2007 R2 не поддерживаются в Lync Server 2013.</P></LI></UL>Чтобы избежать этих проблем, измените расписание собраний, упорядоченных на клиентах Office Communicator 2007 R2 с помощью Outlook 2010 или Outlook 2013, с помощью надстройки "собрание по сети" для Lync 2010 или для собрания по сети для Lync 2013.



</div>

В следующих разделах описаны вопросы, необходимые для развертывания различных типов возможностей Конференции, включая процесс планирования, компоненты, требования к оборудованию и программному обеспечению, а также процесс развертывания.

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор конференц-связи в Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Определение требований для конференц-связи в Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Компоненты и топологии для конференц-связи в Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Технические требования для проведения конференций в Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Контрольный список развертывания для конференций в Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Поддержка больших собраний в Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

