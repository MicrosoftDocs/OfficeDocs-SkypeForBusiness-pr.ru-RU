---
title: Миграция Федерации XMPP
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
ms.openlocfilehash: 61a48c579ed9afa3f1a09ed1c3a7129e9e24924d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Миграция Федерации XMPP

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

