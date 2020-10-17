---
title: 'Lync Server 2013: компоненты, используемые группой ответа'
description: 'Lync Server 2013: компоненты, используемые группой ответа.'
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
ms.openlocfilehash: 2a1e916d9e4bf986bf0337a6f1f1dd918ff2772e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571705"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="f91ce-103">Компоненты, используемые группой ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f91ce-103">Components used by Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f91ce-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="f91ce-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="f91ce-105">Приложение группы ответа автоматически включается при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f91ce-105">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f91ce-106">В этом разделе описываются компоненты, которые поддерживают приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-106">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="f91ce-107">Компоненты группы ответа</span><span class="sxs-lookup"><span data-stu-id="f91ce-107">Response Group Components</span></span>

<span data-ttu-id="f91ce-108">Следующие компоненты Microsoft Lync Server 2013 поддерживают приложение группы ответа:</span><span class="sxs-lookup"><span data-stu-id="f91ce-108">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="f91ce-109">**Служба приложений**     Служба приложений предоставляет платформу для развертывания, хостинга и управления едиными приложениями для обмена мгновенными сообщениями, такими как группа ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="f91ce-110">Служба приложения автоматически устанавливается на каждом сервере переднего плана в интерфейсном пуле и на каждом сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f91ce-110">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="f91ce-111">**Приложение**     группы ответа Приложение группы ответа — это одно из Объединенных приложений для обмена данными, размещаемых в службе приложения.</span><span class="sxs-lookup"><span data-stu-id="f91ce-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="f91ce-112">Он включается автоматически при развертывании группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-112">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="f91ce-113">Приложение группы ответа маршрутизирует и ставит в очередь входящие звонки для групп агентов.</span><span class="sxs-lookup"><span data-stu-id="f91ce-113">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="f91ce-114">**Языковой пакет**     Языковой пакет необходим для поддержки распознавания текста и речи.</span><span class="sxs-lookup"><span data-stu-id="f91ce-114">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="f91ce-115">Эти технологии речи используются при настройке сообщений, например приветственного сообщения и других приглашений, а также вопросов и ответов для система предварительно записанных голосовых сообщений (interactive voice response — IVR).</span><span class="sxs-lookup"><span data-stu-id="f91ce-115">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="f91ce-116">По умолчанию при развертывании Lync Server 2013 устанавливается 26 поддерживаемых языковых пакетов.</span><span class="sxs-lookup"><span data-stu-id="f91ce-116">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f91ce-117">**Звуковые файлы**     Звуковые файлы используются для хранения сообщений и хранения музыки.</span><span class="sxs-lookup"><span data-stu-id="f91ce-117">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="f91ce-118">**Хранилище файлов**     Группа ответа использует хранилище файлов для хранения звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="f91ce-118">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="f91ce-119">Несколько пулов групп ответа могут использовать один и тот же экземпляр хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="f91ce-119">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="f91ce-120">Средство настройки группы **ответа**     Средство настройки группы ответа — это веб-инструмент, который используется для создания и настройки групп ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-120">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="f91ce-121">Средство настройки группы ответа включается при установке веб-служб.</span><span class="sxs-lookup"><span data-stu-id="f91ce-121">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="f91ce-122">Панель управления Microsoft **Lync Server 2013**     Вы можете использовать панель управления Lync Server для настройки и настройки групп агентов и очередей для групп ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-122">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="f91ce-123">**Командная консоль**     Lync Server Все параметры группы ответа можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f91ce-123">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="f91ce-124">**Microsoft Lync 2013**     Формальные агенты (агенты, которые должны войти в группу, прежде чем они смогут принимать звонки для группы), используйте Lync 2013, чтобы войти в группу и выйти из нее.</span><span class="sxs-lookup"><span data-stu-id="f91ce-124">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="f91ce-125">Если группа агентов настроена для формальных агентов, то агенты щелкают элемент меню в Lync 2013, чтобы открыть Internet Explorer и отобразить консоль веб-страниц для входа и выхода из группы.</span><span class="sxs-lookup"><span data-stu-id="f91ce-125">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="f91ce-126">**Веб-службы**     Для средства настройки группы ответа необходимы веб-службы, агенты входа и выхода, панель управления Lync Server и клиентская веб-служба группы ответа.</span><span class="sxs-lookup"><span data-stu-id="f91ce-126">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="f91ce-127">**Клиентская веб-служба**     "группа ответа" Приложение "группа ответа" предоставляет клиентскую веб-службу, которая может использоваться сторонними приложениями для получения сведений об агентах, членстве в группах агентов, состоянии входа агента, состоянии вызова для групп и группах, поддерживающих анонимные вызовы.</span><span class="sxs-lookup"><span data-stu-id="f91ce-127">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="f91ce-128">Lync 2013 и Lync 2010 используйте клиентскую веб-службу для получения списка групп ответа, которые агенты могут использовать для совершения анонимных вызовов.</span><span class="sxs-lookup"><span data-stu-id="f91ce-128">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="f91ce-129">Клиентская веб-служба предоставляется при установке компонента веб-служб.</span><span class="sxs-lookup"><span data-stu-id="f91ce-129">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

