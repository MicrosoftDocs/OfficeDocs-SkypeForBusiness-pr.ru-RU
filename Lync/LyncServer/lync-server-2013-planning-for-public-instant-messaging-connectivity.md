---
title: 'Lync Server 2013: планирование подключения к общедоступным службам обмена мгновенными сообщениями'
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
ms.openlocfilehash: 540173ea468947786e2ead4927ccc66eb2f3ceda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526506"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Планирование подключений к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-10-07_

Общедоступная служба обмена мгновенными сообщениями — это класс Федерации, который позволяет внутренним и внешним пользователям Lync Server 2013 добавлять контакты из следующих компонентов:

  - Контакты Messenger

  - Yahoo\! contacts

  - Контакты America Online (AOL)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>С 1 сентября 2012 г. Лицензия на подписку общедоступных служб обмена мгновенными сообщениями Microsoft Lync (PIC усл) больше недоступна для приобретения новых или обновленных договоров. Клиенты с активными лицензиями смогут продолжать Федерацию с помощью Yahoo! Messenger до даты завершения работы службы. Дата окончания срока жизни 2014 для AOL и Yahoo! объявлено. Дополнительные сведения см <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">в разделе Поддержка общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</P>
> <LI>
> <P>УСЛ PIC — это лицензия на помесячную подписку на уровне пользователя, которая требуется для Lync Server или Office Communications Server для Федерации с Yahoo! Messenger. Способность корпорации Майкрософт предоставлять эту службу зависит от поддержки компании Yahoo!, основного соглашения, для которого обновление не выполняется.</P>
> <LI>
> <P>Lync — это мощное средство для связи между организациями и пользователями мира. Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандарту Lync CAL. В этот список будет добавлена Федерация Skype, которая позволяет пользователям Lync достигать сотни миллионов людей с помощью обмена мгновенными сообщениями и голосовой связи.</P></LI></UL>



</div>

При планировании для этого класса федерации необходимо учитывать следующее:

  - В дополнение к обмену мгновенными сообщениями пользователи Windows Live Messenger могут иметь возможность однорангового аудио-и визуального взаимодействия с пользователями Lync Server 2013. Пограничные серверы должны отвечать определенным требованиям к портам и протоколам. Подробнее: [Определение требований к портам внешнего аудио-и видеоподключения для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - Для обмена мгновенными сообщениями Yahoo не предъявляются уникальные требования, кроме тех, которые обычно используются при планировании и развертывании типичного пограничного сервера, обеспечивающего Федерацию.

  - Для работы в Америке Online необходимо, чтобы сертификат пограничного сервера, назначенный пограничной службе доступа, использовал расширенное использование ключа (EKU) клиента.

<div>

## <a name="in-this-section"></a>Содержание

  - [Сводка по сертификатам: общедоступная служба обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Сводка по портам — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Сводка по DNS — подключение к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

