---
title: 'Lync Server 2013: компоненты, используемые при отправке звонков по группам'
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
ms.openlocfilehash: 0e868ecc20dcafbb5da12c91deb26a91f4efacb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Компоненты, используемые при отправке звонков по группам в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

При развертывании корпоративной голосовой связи и приложения парковки вызовов автоматически разворачивается групповой ответ на звонки. Вы включаете функцию отправки звонков по группам, настраивая таблицу орбит парковки вызовов с отдельными диапазонами номеров, назначенными в качестве номеров группы ответа на звонки, а затем назначая пользователям группы ответа на звонки и предоставление пользователям возможности группового ответа на звонки. Следующие компоненты Lync Server поддерживают отправке звонков групп:

  - ****   Служба приложения службы приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов. Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.

  - **Приложение парковки вызовов**   приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещенных в службе приложения. Группа ответа на звонки основана на приложении парковки вызовов.

  - **Командная консоль**   Lync Server. для управления группами ответа на звонки групп используется Командная консоль Lync Server.

  - **SEFAUtil Resource Kit**   . для назначения пользователей группе ответа на звонки и для включения или отключения функции отправки звонков используется вспомогательная служебная программа активации дополнительных компонентов (SEFAUtil).

</div>

<span> </span>

</div>

</div>

</div>

