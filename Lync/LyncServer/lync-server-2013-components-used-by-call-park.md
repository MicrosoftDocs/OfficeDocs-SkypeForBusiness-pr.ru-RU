---
title: 'Lync Server 2013: компоненты, используемые для парковки вызовов'
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
ms.openlocfilehash: 3b4a833736368fe6060dad4fbb62e6a528e91b6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="aa7af-102">Компоненты, используемые при парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa7af-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa7af-103">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="aa7af-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="aa7af-104">Приложение парковки вызовов устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="aa7af-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="aa7af-105">Парковки вызовов включается путем настройки политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="aa7af-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="aa7af-106">Следующие компоненты Lync Server 2013 поддерживают приложение парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="aa7af-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="aa7af-107">\*\*\*\*   Служба приложения службы приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="aa7af-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="aa7af-108">Служба приложений автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="aa7af-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="aa7af-109">**Приложение парковки вызовов**   приложение парковки вызовов является одним из Объединенных приложений для обмена данными, размещенных в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="aa7af-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="aa7af-110">Оно включается автоматически во время развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="aa7af-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="aa7af-111">Паркс парковки вызовов и получает звонки и управляет орбитами парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="aa7af-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="aa7af-112">**Музыка на удержанных файлах**   если включена функция "Музыка включена", музыкальный файл воспроизводится во время приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="aa7af-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="aa7af-113">При установке приложения парковки вызовов добавляется музыкальный файл по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa7af-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="aa7af-114">**Хранилище файлов.**   приложение парковки вызовов использует хранилище файлов для хранения настраиваемых звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="aa7af-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="aa7af-115">**Панель управления Lync Server**   вы можете использовать панель управления Lync Server, чтобы настроить таблицу орбит парковки вызовов и включить приостановку вызовов для пользователей.</span><span class="sxs-lookup"><span data-stu-id="aa7af-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="aa7af-116">**Консоль управления Lync Server**   . все настройки приложения парковки вызовов можно выполнить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa7af-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

