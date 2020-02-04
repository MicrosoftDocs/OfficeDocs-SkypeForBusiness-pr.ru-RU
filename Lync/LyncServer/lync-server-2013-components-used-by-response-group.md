---
title: 'Lync Server 2013: компоненты, используемые группой ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="816d2-102">Компоненты, используемые группой ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="816d2-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="816d2-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="816d2-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="816d2-104">Приложение группы ответа автоматически включается при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="816d2-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="816d2-105">В этом разделе описаны компоненты, которые поддерживают приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="816d2-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="816d2-106">Компоненты группы ответа</span><span class="sxs-lookup"><span data-stu-id="816d2-106">Response Group Components</span></span>

<span data-ttu-id="816d2-107">Следующие компоненты Microsoft Lync Server 2013 поддерживают приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="816d2-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="816d2-108">\*\*\*\*   Служба приложений службы приложений предоставляет платформу для развертывания и управления приложениями объединенных коммуникаций, например группы ответа.</span><span class="sxs-lookup"><span data-stu-id="816d2-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="816d2-109">Служба приложений автоматически устанавливается на каждый сервер переднего плана в пуле переднего плана и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="816d2-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="816d2-110">**Приложение группы ответа**   приложение "группа ответа" — это одно из унифицированных приложений для обмена данными, размещенных в службе приложений.</span><span class="sxs-lookup"><span data-stu-id="816d2-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="816d2-111">Она включается автоматически при развертывании группы ответа.</span><span class="sxs-lookup"><span data-stu-id="816d2-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="816d2-112">Приложение группы ответа маршрутизирует и помещает в очередь входящие звонки на группы агентов.</span><span class="sxs-lookup"><span data-stu-id="816d2-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="816d2-113">**Языковой пакет**   языковой пакет должен поддерживать распознавание текста и речи.</span><span class="sxs-lookup"><span data-stu-id="816d2-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="816d2-114">Эти технологии речи используются при настройке сообщений, например приветственного сообщения и других приглашений, а также вопросов и ответов системы предварительно записанных голосовых сообщений (IVR).</span><span class="sxs-lookup"><span data-stu-id="816d2-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="816d2-115">По умолчанию при развертывании Lync Server 2013 устанавливаются 26 поддерживаемые языковые пакеты.</span><span class="sxs-lookup"><span data-stu-id="816d2-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="816d2-116">**Звуковые**файлы используются для сообщений и удержания музыки.   </span><span class="sxs-lookup"><span data-stu-id="816d2-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="816d2-117">\*\*\*\*   Группа ответа хранилища файлов использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="816d2-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="816d2-118">Несколько пулов групп ответа могут использовать один и тот же экземпляр хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="816d2-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="816d2-119">**Средство настройки группы**   ответа средство настройки группы ответа — это веб-инструмент, который используется для создания и настройки групп ответа.</span><span class="sxs-lookup"><span data-stu-id="816d2-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="816d2-120">Средство настройки группы ответа включается при установке веб-служб.</span><span class="sxs-lookup"><span data-stu-id="816d2-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="816d2-121">**Панель управления Microsoft Lync Server 2013**   можно использовать панель управления Lync Server для настройки и настройки групп агентов и очередей для групп ответов.</span><span class="sxs-lookup"><span data-stu-id="816d2-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="816d2-122">**В командной**   консоли Lync Server можно настроить все параметры группы ответа с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="816d2-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="816d2-123">**Microsoft Lync 2013**   formal Agents (агенты, которые должны входить в группу до того, как они смогут получать звонки для группы) используйте Lync 2013 для входа в группу и выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="816d2-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="816d2-124">Если группа агента настроена для формальных агентов, то агенты щелкают элемент меню в Lync 2013, чтобы открыть Internet Explorer и отобразить консоль веб-страницы для входа и выхода из нее.</span><span class="sxs-lookup"><span data-stu-id="816d2-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="816d2-125">**Веб-** службы, необходимые для средства настройки группы ответа, консоли входа и выхода из нее, панели управления Lync Server и клиентской веб-службой группы ответа.   </span><span class="sxs-lookup"><span data-stu-id="816d2-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="816d2-126">\*\*\*\*   Группа ответа "клиент" в группе ответа приложение предоставляет веб-службу клиента, которая может использоваться сторонними приложениями для получения сведений об агентах, членстве в группах агента, состоянии входа агента, состоянии вызова для групп и группах, поддерживающих анонимные вызовы.</span><span class="sxs-lookup"><span data-stu-id="816d2-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="816d2-127">В Lync 2013 и Lync 2010 вы можете использовать веб-службу клиента группы ответа для получения списка групп ответов, которые агенты могут использовать для анонимных вызовов.</span><span class="sxs-lookup"><span data-stu-id="816d2-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="816d2-128">Веб-служба клиента включается при установке веб-служб.</span><span class="sxs-lookup"><span data-stu-id="816d2-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

