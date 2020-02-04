---
title: 'Lync Server 2013: планирование подключения общедоступной службы обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Планирование подключения общедоступной службы обмена мгновенными сообщениями в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-10-07_

Общедоступная служба обмена мгновенными сообщениями является классом Федерации и настроена на разрешение внутренних и внешних пользователей Lync Server 2013 для добавления контактов из указанных ниже вариантов.

  - Контакты Messenger

  - Yahoo\! контакты,

  - Контакты из Skype Online (AOL)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>За Сентябрь 1 сентября 2012 г. Лицензия на подписку на общедоступные пользователи Microsoft Lync (PIC усл) больше не доступна для приобретения новых или обновленных договоров. Пользователи с активными лицензиями смогут продолжать использовать федерацию с помощью Yahoo! Messenger, пока не зайдет Дата завершения обслуживания. Дата окончания жизненного цикла 2014 для AOL и Yahoo! в течение июня. было объявлено. Подробности можно найти <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</P>
> <LI>
> <P>УСЛ PIC является лицензией на подписку "на пользователя", которая требуется для использования Lync Server или Office Communications Server для Федерации с помощью Yahoo! Messenger. Возможность предоставления этой услуги корпорацией Майкрософт зависит от поддержки компании Yahoo!, основного соглашения, для которого она не будет продлена.</P>
> <LI>
> <P>В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру. Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств за пределами стандартной клиентской лицензии Lync. В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут получать сотни миллионов людей с помощью голосовой почты и голосовых сообщений.</P></LI></UL>



</div>

Для этого класса Федерации требуются следующие вопросы планирования:

  - Пользователи Windows Live Messenger могут иметь доступ к одноранговой голосовой и видеосвязи с пользователями Lync Server 2013, а также обмениваться мгновенными сообщениями. Пограничные серверы должны соответствовать конкретным требованиям к порту и протоколу. Подробности можно найти [в разделе Определение внешних параметров брандмауэра/V и требований к портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - В обмене сообщениями Yahoo нет уникальных требований, кроме тех, которые обычно используются при планировании и развертывании типичного пограничного сервера, предоставляющего Федерацию.

  - Для использования Skype Online требуется, чтобы сертификат пограничного сервера, назначенный службе EDGE, использовал улучшенное использование ключа (EKU).

<div>

## <a name="in-this-section"></a>Содержание

  - [Сведения о сертификате: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Сводка DNS: подключение общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

