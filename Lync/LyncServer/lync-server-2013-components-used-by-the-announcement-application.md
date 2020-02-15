---
title: 'Lync Server 2013: компоненты, используемые приложением "объявление"'
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
ms.openlocfilehash: a888ca21e26a21103d1c45e74518c3d224d18a7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="21fe7-102">Компоненты, используемые приложением "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21fe7-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21fe7-103">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="21fe7-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="21fe7-104">В Lync Server 2013 приложение извещения является компонентом приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="21fe7-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="21fe7-105">При развертывании корпоративной голосовой связи приложение извещения автоматически устанавливается и активируется вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="21fe7-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="21fe7-106">В этом разделе описываются компоненты, поддерживающие приложение "извещения".</span><span class="sxs-lookup"><span data-stu-id="21fe7-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="21fe7-107">Компоненты приложения "Объявление"</span><span class="sxs-lookup"><span data-stu-id="21fe7-107">Announcement Application Components</span></span>

<span data-ttu-id="21fe7-108">Следующие компоненты Lync Server поддерживают приложение извещения:</span><span class="sxs-lookup"><span data-stu-id="21fe7-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="21fe7-109">\*\*\*\*   Служба приложения службы приложений предоставляет платформу для развертывания и управления приложениями единой системы обмена сообщениями, а также для управления ими.</span><span class="sxs-lookup"><span data-stu-id="21fe7-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="21fe7-110">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="21fe7-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="21fe7-111">**Приложение группы ответа**   приложение группы ответа является одним из Объединенных приложений для обмена данными, размещаемых в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="21fe7-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="21fe7-112">Если диапазон неназначенных номеров телефонов настроен для маршрутизации к уведомлению, приложение группы ответа необходимо для маршрутизации вызовов, выполненных на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="21fe7-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="21fe7-113">(Приложение группы ответа не требуется, если все диапазоны настроены для маршрутизации в единую систему обмена сообщениями Exchange (единой системы обмена сообщениями).)</span><span class="sxs-lookup"><span data-stu-id="21fe7-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="21fe7-114">\*\*\*\*   Звуковые файлы звуковых файлов используются для объявлений.</span><span class="sxs-lookup"><span data-stu-id="21fe7-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="21fe7-115">**Хранилище файлов.**   приложение извещения использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="21fe7-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="21fe7-116">**Панель управления Lync Server**   панель управления Lync Server можно использовать для настройки таблицы неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="21fe7-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="21fe7-117">**Командная консоль**   Lync Server с помощью командлетов командной консоли Lync Server можно настроить параметры оповещений и таблицу неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="21fe7-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

