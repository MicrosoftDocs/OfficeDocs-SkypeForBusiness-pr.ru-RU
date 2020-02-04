---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Перенос федерации XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Предыдущие версии Lync Server и Office Communications Server предоставили шлюз расширенных сообщений и протоколов доступа (КСМПП), который можно развернуть как отдельную серверную роль, разрешающую Федерацию с помощью КСМППных развертываний. В Lync Server 2013 функциональность КСМПП может быть развернута как функция. Функции КСМПП устанавливаются в виде прокси-сервера КСМПП, который работает на пограничном сервере Lync Server 2013 и шлюз КСМПП, который работает на сервере переднего плана Lync Server 2013.

С точки зрения миграции учетная запись пользователя Lync Server может быть перемещена в пул Lync Server 2013 и продолжать использовать устаревший шлюз КСМПП. Это возможно, только если для федеративного партнера КСМПП не настроена платформа Lync Server 2013.

В сводке, если Lync Server 2010 был развернут с помощью шлюза Office Communications Server 2007 R2 КСМПП Gateway и КСМПП Federation для пользователей Lync Server 2010, чтобы перенести КСМППную Федерацию на Lync Server 2013, выполните указанные ниже действия.

1.  Развертывание пула Lync Server 2013.

2.  Разверните сервер Lync Server 2013 Edge.

3.  Перемещение всех пользователей в пул Lync Server 2013

4.  Создавайте политики доступа КСМПП и сертификаты для пограничного сервера.

5.  Включите Федерацию КСМПП в Lync Server 2013. 

6.  Обновите записи DNS, чтобы они указывали на сервер Lync Server 2013 КСМПП Gateway.

</div>

<span> </span>

</div>

</div>

</div>

