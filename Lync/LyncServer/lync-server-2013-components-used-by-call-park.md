---
title: 'Lync Server 2013: компоненты, используемые парковкой вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="6983c-102">Компоненты, используемые парковкой вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6983c-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6983c-103">_**Тема последнего изменения:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="6983c-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="6983c-104">Приложение для парковки звонков устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6983c-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6983c-105">Вы включаете приостановку звонков с помощью настройки политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6983c-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="6983c-106">Следующие компоненты Lync Server 2013 поддерживают приложение для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="6983c-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="6983c-107">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания и управления едиными приложениями для обмена информацией, например с помощью приложения для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="6983c-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="6983c-108">Служба приложений устанавливается автоматически на каждый сервер переднего плана в пуле переднего плана и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6983c-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="6983c-109">**Приложение для приостановки звонков**   . приложение для приема звонков — одно из унифицированных приложений для обмена данными, размещенных в службе приложений.</span><span class="sxs-lookup"><span data-stu-id="6983c-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="6983c-110">Она включается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6983c-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="6983c-111">Звоните в парки и загружает звонки и управляет орбитами.</span><span class="sxs-lookup"><span data-stu-id="6983c-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="6983c-112">**Музыка на удержании**   . Если включена музыка, музыкальный файл воспроизводится во время приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="6983c-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="6983c-113">Музыкальный файл по умолчанию включается, когда установлено приложение для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="6983c-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="6983c-114">**Хранение файлов.**   в приложении парковки используется хранилище файлов, в котором хранятся пользовательские звуковые файлы.</span><span class="sxs-lookup"><span data-stu-id="6983c-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="6983c-115">**Панель управления Lync Server**   . Вы можете использовать панель управления Lync Server для настройки таблицы с приостановкой по орбите и включить приостановку звонков для пользователей.</span><span class="sxs-lookup"><span data-stu-id="6983c-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="6983c-116">**Командная консоль Lync Server Management Shell**   для настройки приложения на приостановке звонков можно использовать командлеты командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6983c-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

