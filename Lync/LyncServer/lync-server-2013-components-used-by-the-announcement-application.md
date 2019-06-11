---
title: 'Lync Server 2013: компоненты, используемые приложением "Объявление"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e8e4a0fdfe0dcdd69a3f371aed338caf7f73348
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="1f990-102">Компоненты, используемые приложением "Объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f990-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f990-103">_**Тема последнего изменения:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="1f990-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="1f990-104">В Lync Server 2013 приложение извещения является компонентом приложения "группа ответа".</span><span class="sxs-lookup"><span data-stu-id="1f990-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="1f990-105">При развертывании корпоративной голосовой связи приложение извещения автоматически устанавливается и активируется вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="1f990-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="1f990-106">В этом разделе описаны компоненты, которые поддерживают приложение извещения.</span><span class="sxs-lookup"><span data-stu-id="1f990-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="1f990-107">Компоненты приложения объявлений</span><span class="sxs-lookup"><span data-stu-id="1f990-107">Announcement Application Components</span></span>

<span data-ttu-id="1f990-108">Следующие компоненты Lync Server поддерживают приложение извещения:</span><span class="sxs-lookup"><span data-stu-id="1f990-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="1f990-109">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания и управления едиными приложениями для обмена информацией.</span><span class="sxs-lookup"><span data-stu-id="1f990-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="1f990-110">Служба приложений устанавливается автоматически на каждый сервер переднего плана в пуле переднего плана и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1f990-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="1f990-111">**Приложение группы ответа**   приложение "группа ответа" — это одно из унифицированных приложений для обмена данными, размещенных в службе приложений.</span><span class="sxs-lookup"><span data-stu-id="1f990-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="1f990-112">Если диапазон номеров телефона, для которого задано значение, настроен для маршрутизации к объявлению, приложение группы ответа необходимо для направления звонков на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="1f990-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="1f990-113">(Приложение группы ответа не требуется, если все диапазоны настроены для маршрутизации в единую систему обмена сообщениями Exchange (UM).)</span><span class="sxs-lookup"><span data-stu-id="1f990-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="1f990-114">\*\*\*\* Звуковые файлы используются для извещений.   </span><span class="sxs-lookup"><span data-stu-id="1f990-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="1f990-115">**Хранилище файлов.**   приложение извещения использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="1f990-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="1f990-116">**Панель управления Lync Server**   . для настройки таблицы неназначенные номера можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f990-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="1f990-117">**Командная консоль**   Lync Server. Вы можете использовать командлеты командной консоли Lync Server для настройки объявлений и неназначенных числовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="1f990-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

