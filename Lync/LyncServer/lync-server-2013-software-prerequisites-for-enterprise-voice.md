---
title: 'Lync Server 2013: необходимое программное обеспечение для корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc6c5e5f3f9fc92f56ee1f044419f67f5ded32ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Необходимое программное обеспечение для корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

Убедитесь в том, что инфраструктура, в которой вы планируете развертывать корпоративную голосовую связь, соответствует следующим предварительным требованиям к программному обеспечению.

  - Lync Server 2013 Standard Edition или Enterprise Edition установлен и работает в вашей сети.

  - Все пограничные серверы развернуты и работают в сети периметра, включая пограничные серверы, на которых работает пограничная служба доступа, пограничная служба аудио-и видеоконференций, пограничная служба веб-конференций и обратный прокси-сервер.

  - Microsoft Exchange Server 2007 с пакетом обновления 3 (SP3), Microsoft Exchange Server 2010 или Microsoft Exchange Server 2013 требуется для интеграции единой системы обмена сообщениями Exchange с Lync Server, а также для предоставления расширенных уведомлений и сведений о журналах вызовов для Конечные точки Lync.

  - Один или несколько пользователей были созданы и включены для Lync Server.

  - Клиенты и устройства Lync успешно развернуты.

  - Построитель топологий установлен на сервере в сети.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Дальнейшие действия: проверка выполнения требований к безопасности и конфигурации

Проверив выполнение требований к программному обеспечению, вы можете продолжить подготовку к развертыванию корпоративной голосовой связи с помощью этой документации.

1.  Проверьте безопасность, конфигурацию пользователя и оборудование перкуиситес, как описано в статье [требования к безопасности и конфигурации для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Установите сервер-посредник, как описано в [статье Установка файлов для сервера-посредника в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), но *только* в том случае, если требуется развернуть автономный сервер-посредник или пул, так как серверы-посредники устанавливаются как часть пула переднего плана или процесса развертывания сервера Standard Edition при совместном размещении.

3.  Настройте магистральные подключения для предоставления доступа к PSTN для пользователей, как описано в разделе [Настройка магистральных каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

