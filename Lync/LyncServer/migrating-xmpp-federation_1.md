---
title: Перенос федерации XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Перенос федерации XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

Предыдущие версии Office Communications Server предоставили шлюз XMPP (Extensible Messaging and Presence Protocol), который можно развернуть как отдельную роль сервера, чтобы разрешить федерацию с развертываниями XMPP. В Lync Server 2013 функция XMPP может быть развернута в качестве компонента. Функции XMPP установлены в двух частях: в качестве прокси-сервера XMPP, работающего на пограничном сервере Lync Server 2013, и шлюза XMPP, работающего на сервере переднего плана Lync Server 2013.

С точки зрения миграции учетная запись пользователя Office Communications Server 2007 R2 может быть перемещена в пул Lync Server 2013 и продолжать использовать шлюз Office Communications Server 2007 R2 XMPP. Это возможно только в том случае, если федеративный партнер XMPP не настроен в Lync Server 2013.

В целом, если сервер Office Communications Server был развернут с шлюзом Office Communications Server 2007 R2 XMPP и для Федерации XMPP включена поддержка устаревших пользователей Office Communications Server 2007 R2, для переноса Федерации XMPP в Lync Server 2013:

1.  Разверните пул Lync Server 2013.

2.  Развертывание пограничного сервера Lync Server 2013.

3.  Переместите всех пользователей в пул Lync Server 2013.

4.  Создайте сертификаты и политики доступа XMPP для пограничного сервера.

5.  Включите Федерацию XMPP в Lync Server 2013. 

6.  Обновите записи DNS, чтобы они ссылались на шлюз XMPP Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

