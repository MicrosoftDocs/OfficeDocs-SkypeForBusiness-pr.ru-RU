---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Перенос федерации XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

Предыдущие версии Office Communications Server предоставили шлюз расширенных сообщений и протокол присутствия (КСМПП), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с помощью КСМППных развертываний. В Lync Server 2013 функциональность КСМПП может быть развернута как функция. Функции КСМПП устанавливаются в виде прокси-сервера КСМПП, который работает на пограничном сервере Lync Server 2013 и шлюз КСМПП, который работает на сервере переднего плана Lync Server 2013.

С точки зрения миграции учетная запись пользователя Office Communications Server 2007 R2 может быть перенесена в пул Lync Server 2013 и продолжать использовать шлюз Office Communications Server 2007 R2 КСМПП Gateway. Это возможно, только если для федеративного партнера КСМПП не настроена платформа Lync Server 2013.

Если вы развернули Office Communications Server с помощью шлюза Office Communications Server 2007 R2 КСМПП Gateway и КСМПП Federation для пользователей Office Communications Server 2007 R2, перенесите КСМПП Федерацию на Lync Server 2013.

1.  Развертывание пула Lync Server 2013.

2.  Разверните сервер Lync Server 2013 Edge.

3.  Переместите всех пользователей в пул Lync Server 2013.

4.  Создавайте политики доступа КСМПП и сертификаты для пограничного сервера.

5.  Включите Федерацию КСМПП в Lync Server 2013. 

6.  Обновите записи DNS, чтобы они указывали на сервер Lync Server 2013 КСМПП Gateway.

</div>

<span> </span>

</div>

</div>

</div>

