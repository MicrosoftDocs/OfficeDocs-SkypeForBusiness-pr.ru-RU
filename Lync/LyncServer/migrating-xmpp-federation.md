---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0567f5c2173b1c0d476367d5ab9a70f4c630aa82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527356"
---
# <a name="migrating-xmpp-federation"></a>Перенос федерации XMPP

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Предыдущие версии Lync Server и Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который может быть развернут как отдельная роль сервера, чтобы разрешить федерацию с развертываниями XMPP. В Lync Server 2013 функция XMPP может быть развернута в качестве компонента. Функции XMPP установлены в двух частях: в качестве прокси-сервера XMPP, работающего на пограничном сервере Lync Server 2013, и шлюза XMPP, работающего на сервере переднего плана Lync Server 2013.

С точки зрения миграции учетная запись пользователя Lync Server может быть перемещена в пул Lync Server 2013 и продолжать использовать устаревший шлюз XMPP. Это возможно только в том случае, если федеративный партнер XMPP не настроен в Lync Server 2013.

В целом, если Lync Server 2010 был развернут с шлюзом Office Communications Server 2007 R2 XMPP и для Федерации XMPP включен доступ к старым пользователям Lync Server 2010, для переноса Федерации XMPP в Lync Server 2013:

1.  Разверните пул Lync Server 2013.

2.  Развертывание пограничного сервера Lync Server 2013.

3.  Перемещение всех пользователей в пул Lync Server 2013

4.  Создайте сертификаты и политики доступа XMPP для пограничного сервера.

5.  Включите Федерацию XMPP в Lync Server 2013. 

6.  Обновите записи DNS, чтобы они ссылались на шлюз XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

