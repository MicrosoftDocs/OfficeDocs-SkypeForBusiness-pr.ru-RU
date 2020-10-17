---
title: 'Lync Server 2013: компоненты, используемые при отправке звонков по группам'
description: 'Lync Server 2013: компоненты, используемые при отправке звонков по группам.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517f75dcbac8bfed0e749c061a9696b7667e10ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571835"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Компоненты, используемые при отправке звонков по группам в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

При развертывании корпоративной голосовой связи и приложения парковки вызовов автоматически разворачивается групповой ответ на звонки. Вы включаете функцию отправки звонков по группам, настраивая таблицу орбит парковки вызовов с отдельными диапазонами номеров, назначенными в качестве номеров группы ответа на звонки, а затем назначая пользователям группы ответа на звонки и предоставление пользователям возможности группового ответа на звонки. Следующие компоненты Lync Server поддерживают отправке звонков групп:

  - **Служба приложений**     Служба приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов. Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.

  - **Приложение**     парковки вызовов Приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещаемых в службе приложения. Группа ответа на звонки основана на приложении парковки вызовов.

  - **Командная консоль**     Lync Server Консоль управления Lync Server используется для управления группами ответа на звонки групп.

  - **SEFAUtil Resource Kit Tool**     С помощью служебной программы активации дополнительных компонентов (SEFAUtil) можно назначить пользователей для группы ответа на звонки, а также включить или отключить функцию сбора вызовов для пользователей.

</div>

<span> </span>

</div>

</div>

</div>

