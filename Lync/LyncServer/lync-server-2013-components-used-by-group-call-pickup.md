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
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="9b82f-103">Компоненты, используемые при отправке звонков по группам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b82f-103">Components used by Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b82f-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9b82f-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9b82f-105">При развертывании корпоративной голосовой связи и приложения парковки вызовов автоматически разворачивается групповой ответ на звонки.</span><span class="sxs-lookup"><span data-stu-id="9b82f-105">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="9b82f-106">Вы включаете функцию отправки звонков по группам, настраивая таблицу орбит парковки вызовов с отдельными диапазонами номеров, назначенными в качестве номеров группы ответа на звонки, а затем назначая пользователям группы ответа на звонки и предоставление пользователям возможности группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="9b82f-106">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="9b82f-107">Следующие компоненты Lync Server поддерживают отправке звонков групп:</span><span class="sxs-lookup"><span data-stu-id="9b82f-107">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="9b82f-108">**Служба приложений**     Служба приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="9b82f-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="9b82f-109">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9b82f-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="9b82f-110">**Приложение**     парковки вызовов Приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещаемых в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="9b82f-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="9b82f-111">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="9b82f-111">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="9b82f-112">**Командная консоль**     Lync Server Консоль управления Lync Server используется для управления группами ответа на звонки групп.</span><span class="sxs-lookup"><span data-stu-id="9b82f-112">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="9b82f-113">**SEFAUtil Resource Kit Tool**     С помощью служебной программы активации дополнительных компонентов (SEFAUtil) можно назначить пользователей для группы ответа на звонки, а также включить или отключить функцию сбора вызовов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9b82f-113">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

