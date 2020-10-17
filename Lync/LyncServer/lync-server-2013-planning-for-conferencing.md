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
ms.openlocfilehash: 6bf1bf0ce10281bf4d31fc8fdb1be9251b72caf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507026"
---
# <a name="planning-for-conferencing-in-lync-server-2013"></a>Планирование конференц-связи в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-29_

Lync Server 2013 предоставляет богатый набор возможностей для конференц-связи:

  - Веб-конференции, включающие совместную работу с документами, общий доступ к приложениям и общий доступ к рабочему столу. Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки совместного использования и отрисовки презентаций PowerPoint. Дополнительные сведения об установке и настройке сервера Office Web Apps приведены в статье [Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Аудио-и видеоконференции (A/V), которые позволяют пользователям осуществлять аудио-и видеоконференции в реальном времени, не требуя использования внешних служб, таких как служба Microsoft Live Meeting или сторонний звуковой мост.

  - Конференц-связь с телефонным подключением, которая позволяет пользователям присоединяться к звуковой части конференции Lync Server 2013 с помощью телефонного телефона общего пользования (PSTN), не требуя использования стороннего поставщика услуг голосовой связи.

  - Конференц-связь с обменом мгновенными сообщениями, в которой более двух сторон обмениваются сообщениями в едином сеансе обмена мгновенными сообщениями. Подробные сведения о конференц-связи можно найти [в статье Планирование для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 поддерживает как запланированные, так и конференции случайные.

При развертывании Lync Server 2013, сервер переднего плана вы можете выбрать, следует ли развертывать веб-конференции, аудио-и видеоконференции, а также возможности конференц-связи с телефонным подключением. Возможности конференц-связи с IM всегда развертываются автоматически вместе с возможностями обмена мгновенными сообщениями на серверах переднего плана Lync Server 2013.

<div>


> [!NOTE]  
> Если развертывание включает собрания, упорядоченные с помощью клиентов Office Communicator 2007 R2 (включая консоль Live Meeting или надстройка конференц-связи для Microsoft Office Outlook), то после переноса на Lync Server 2013 будут иметься следующие ограничения. 
> <UL>
> <LI>
> <P>Пользователи на собрании не смогут использовать функции совместной работы с данными, в том числе совместную работу с документами, общий доступ к приложениям и общий доступ к рабочему столу.</P>
> <LI>
> <P>Проблемы с стабильностью могут возникать, так как клиенты Office Communicator 2007 R2 не поддерживаются в Lync Server 2013.</P></LI></UL>Чтобы избежать этих проблем, Перепланируйте собрание, упорядоченное с помощью клиентов Office Communicator 2007 R2 с Outlook 2010 или Outlook 2013, с помощью надстройки "собрание по сети" для Lync 2010 или "собрание по сети" для Lync 2013.



</div>

В следующих разделах описывается, что необходимо для развертывания различных типов возможностей конференц-связи, включая процесс планирования, компоненты, требования к оборудованию и программному обеспечению, а также процесс развертывания.

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор конференц-связи в Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Определение требований для конференц-связи в Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Компоненты и топологии для конференц-связи в Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Технические требования для конференц-связи в Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Контрольный список развертывания для конференц-связи в Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Поддержка больших собраний в Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

