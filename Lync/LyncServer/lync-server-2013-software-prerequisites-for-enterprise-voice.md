---
title: 'Lync Server 2013: необходимое программное обеспечение для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Необходимое программное обеспечение для корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-03_

Убедитесь в том, что инфраструктура, в которой вы планируете развернуть корпоративный голос, соответствует следующим требованиям к программному обеспечению.

  - Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в сети.

  - Все пограничные серверы развертываются и работают в демилитаризованной зоне, в том числе на пограничные серверы, на которых работает служба EDGE, служба EDGE, служба Edge для веб-конференций и обратный прокси.

  - Microsoft Exchange Server 2007 с пакетом обновления 3 (SP3), Microsoft Exchange Server 2010 или Microsoft Exchange Server 2013 требуется для интеграции единой системы обмена сообщениями Exchange с сервером Lync, а также для предоставления подробных уведомлений и ведения журнала звонков Конечные точки Lync.

  - У вас есть один или несколько пользователей, которые были созданы и включены для Lync Server.

  - Клиенты и устройства Lync успешно развернуты.

  - Построитель топологии установлен на сервере в сети.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Дальнейшие действия: Проверка требований к безопасности и конфигурации

После проверки требований к программному обеспечению для корпоративной голосовой связи вы можете использовать документацию для продолжения подготовки к развертыванию корпоративной голосовой связи:

1.  Проверьте безопасность, конфигурацию пользователя и оборудование перкуиситес, как описано в разделе [требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Установите сервер-посредник, как описано в разделе [Установка сервера исправлений в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), но *только* в том случае, если вы хотите развернуть изолированный сервер или пул, так как серверы обновлений устанавливаются в рамках пула переднего плана или Процесс развертывания сервера Standard Edition при совместном использовании.

3.  Настройте магистральные подключения для предоставления доступа к PSTN для пользователей, как описано в разделе [Настройка каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

