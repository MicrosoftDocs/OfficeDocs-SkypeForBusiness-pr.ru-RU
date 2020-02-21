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

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f7af4-102">Компоненты, используемые при отправке звонков по группам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7af4-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7af4-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f7af4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f7af4-104">При развертывании корпоративной голосовой связи и приложения парковки вызовов автоматически разворачивается групповой ответ на звонки.</span><span class="sxs-lookup"><span data-stu-id="f7af4-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="f7af4-105">Вы включаете функцию отправки звонков по группам, настраивая таблицу орбит парковки вызовов с отдельными диапазонами номеров, назначенными в качестве номеров группы ответа на звонки, а затем назначая пользователям группы ответа на звонки и предоставление пользователям возможности группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="f7af4-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="f7af4-106">Следующие компоненты Lync Server поддерживают отправке звонков групп:</span><span class="sxs-lookup"><span data-stu-id="f7af4-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="f7af4-107">\*\*\*\*   Служба приложения службы приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f7af4-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="f7af4-108">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f7af4-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="f7af4-109">**Приложение парковки вызовов**   приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещенных в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="f7af4-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="f7af4-110">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f7af4-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="f7af4-111">**Командная консоль**   Lync Server. для управления группами ответа на звонки групп используется Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7af4-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="f7af4-112">**SEFAUtil Resource Kit**   . для назначения пользователей группе ответа на звонки и для включения или отключения функции отправки звонков используется вспомогательная служебная программа активации дополнительных компонентов (SEFAUtil).</span><span class="sxs-lookup"><span data-stu-id="f7af4-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

