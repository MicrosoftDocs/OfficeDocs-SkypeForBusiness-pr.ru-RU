---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a36e92849c59760f831cdebaf59906b546b01d7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a>Проверка федерации и удаленного доступа для внешних пользователей

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-18_

После переноса маршрута Федерации на пограничный сервер Lync Server 2013 необходимо выполнить некоторые функциональные тесты, чтобы убедиться, что Федерация работает должным образом. В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Тест подключения внешних пользователей и внешнего доступа

  - Пользователи, по крайней мере, один федеративный домен, внутренний пользователь Lync Server 2013 и пользователь в Lync Server 2010. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.

  - Пользователи каждого общедоступного поставщика услуг обмена мгновенными сообщениями, поддерживаемого организацией (и для которого была выполнена подготовка), взаимодействуют с пользователем в Lync Server 2013 и пользователем в Lync Server 2010.

  - Проверьте, что анонимные пользователи могут присоединиться к конференциям.

  - Пользователь, размещенный на Lync Server 2010, использующий удаленный доступ пользователей (вход в Lync Server 2010 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователем Lync Server 2010. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.

  - Пользователь, размещенный на Lync Server 2013, использующий удаленный доступ пользователей (вход в Lync Server 2013 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователем Lync Server 2010. Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.

</div>

</div>

<span> </span>

</div>

</div>

</div>

