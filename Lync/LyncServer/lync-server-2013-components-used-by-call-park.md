---
title: 'Lync Server 2013: компоненты, используемые для парковки вызовов'
description: 'Lync Server 2013: компоненты, используемые для парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576775"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="8d228-103">Компоненты, используемые при парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d228-103">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d228-104">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="8d228-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="8d228-105">Приложение парковки вызовов устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8d228-105">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8d228-106">Парковки вызовов включается путем настройки политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8d228-106">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="8d228-107">Следующие компоненты Lync Server 2013 поддерживают приложение парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="8d228-107">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="8d228-108">**Служба приложений**     Служба приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8d228-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="8d228-109">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8d228-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="8d228-110">**Приложение**     парковки вызовов Приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещаемых в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="8d228-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="8d228-111">Оно включается автоматически во время развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8d228-111">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="8d228-112">Паркс парковки вызовов и получает звонки и управляет орбитами парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8d228-112">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="8d228-113">**Музыкальный файл**     на удержании Если включена функция "Музыка включена", музыкальный файл воспроизводится во время приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="8d228-113">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="8d228-114">При установке приложения парковки вызовов добавляется музыкальный файл по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d228-114">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="8d228-115">**Хранилище файлов**     Приложение парковки вызовов использует хранилище файлов для хранения настраиваемых звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="8d228-115">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="8d228-116">Панель управления Lync **Server**     С помощью панели управления Lync Server можно настроить таблицу орбит парковки вызовов и включить приостановку вызовов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8d228-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="8d228-117">**Командная консоль**     Lync Server Все настройки приложения парковки вызовов можно выполнить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d228-117">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

