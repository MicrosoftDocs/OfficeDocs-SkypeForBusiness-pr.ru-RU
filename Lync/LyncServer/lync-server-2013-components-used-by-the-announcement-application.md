---
title: 'Lync Server 2013: компоненты, используемые приложением "Объявление"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="79557-102">Компоненты, используемые приложением "Объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79557-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79557-103">_**Тема последнего изменения:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="79557-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="79557-104">В Lync Server 2013 приложение извещения является компонентом приложения "группа ответа".</span><span class="sxs-lookup"><span data-stu-id="79557-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="79557-105">При развертывании корпоративной голосовой связи приложение извещения автоматически устанавливается и активируется вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="79557-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="79557-106">В этом разделе описаны компоненты, которые поддерживают приложение извещения.</span><span class="sxs-lookup"><span data-stu-id="79557-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="79557-107">Компоненты приложения объявлений</span><span class="sxs-lookup"><span data-stu-id="79557-107">Announcement Application Components</span></span>

<span data-ttu-id="79557-108">Следующие компоненты Lync Server поддерживают приложение извещения:</span><span class="sxs-lookup"><span data-stu-id="79557-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="79557-109">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания и управления едиными приложениями для обмена информацией.</span><span class="sxs-lookup"><span data-stu-id="79557-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="79557-110">Служба приложений устанавливается автоматически на каждый сервер переднего плана в пуле переднего плана и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="79557-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="79557-111">**Приложение группы ответа**   приложение "группа ответа" — это одно из унифицированных приложений для обмена данными, размещенных в службе приложений.</span><span class="sxs-lookup"><span data-stu-id="79557-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="79557-112">Если диапазон номеров телефона, для которого задано значение, настроен для маршрутизации к объявлению, приложение группы ответа необходимо для направления звонков на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="79557-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="79557-113">(Приложение группы ответа не требуется, если все диапазоны настроены для маршрутизации в единую систему обмена сообщениями Exchange (UM).)</span><span class="sxs-lookup"><span data-stu-id="79557-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="79557-114">**Звуковые**файлы используются для извещений.   </span><span class="sxs-lookup"><span data-stu-id="79557-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="79557-115">**Хранилище файлов.**   приложение извещения использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="79557-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="79557-116">**Панель управления Lync Server**   . для настройки таблицы неназначенные номера можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79557-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="79557-117">**Командная консоль**   Lync Server. Вы можете использовать командлеты командной консоли Lync Server для настройки объявлений и неназначенных числовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="79557-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

