---
title: 'Lync Server 2013: компоненты, используемые приложением "объявление"'
description: 'Lync Server 2013: компоненты, используемые приложением "извещения".'
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
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577695"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="9b097-103">Компоненты, используемые приложением "объявление" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b097-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b097-104">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="9b097-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="9b097-105">В Lync Server 2013 приложение извещения является компонентом приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9b097-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="9b097-106">При развертывании корпоративной голосовой связи приложение извещения автоматически устанавливается и активируется вместе с приложением группы ответа.</span><span class="sxs-lookup"><span data-stu-id="9b097-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="9b097-107">В этом разделе описываются компоненты, поддерживающие приложение "извещения".</span><span class="sxs-lookup"><span data-stu-id="9b097-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="9b097-108">Компоненты приложения "Объявление"</span><span class="sxs-lookup"><span data-stu-id="9b097-108">Announcement Application Components</span></span>

<span data-ttu-id="9b097-109">Следующие компоненты Lync Server поддерживают приложение извещения:</span><span class="sxs-lookup"><span data-stu-id="9b097-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="9b097-110">**Служба приложений**     Служба приложений предоставляет платформу для развертывания и управления приложениями единой системы обмена сообщениями, а также для их разхостинга и управления ими.</span><span class="sxs-lookup"><span data-stu-id="9b097-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="9b097-111">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9b097-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="9b097-112">**Приложение**     группы ответа Приложение группы ответа — это одно из Объединенных приложений для обмена данными, размещаемых в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="9b097-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="9b097-113">Если диапазон неназначенных номеров телефонов настроен для маршрутизации к уведомлению, приложение группы ответа необходимо для маршрутизации вызовов, выполненных на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="9b097-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="9b097-114">(Приложение группы ответа не требуется, если все диапазоны настроены для маршрутизации в единую систему обмена сообщениями Exchange (единой системы обмена сообщениями).)</span><span class="sxs-lookup"><span data-stu-id="9b097-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="9b097-115">**Звуковые файлы**     Звуковые файлы используются для объявлений.</span><span class="sxs-lookup"><span data-stu-id="9b097-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="9b097-116">**Хранилище файлов**     Приложение извещения использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="9b097-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="9b097-117">Панель управления Lync **Server**     Для настройки таблицы неназначенных номеров можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b097-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="9b097-118">**Командная консоль**     Lync Server С помощью командлетов командной консоли Lync Server можно настроить параметры оповещений и таблицу неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="9b097-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

