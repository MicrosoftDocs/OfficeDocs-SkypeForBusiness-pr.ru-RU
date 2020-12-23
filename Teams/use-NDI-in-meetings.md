---
title: Использование NDI в Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как использовать NDI в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337018"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="1e2c1-103">Использование NDI® в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e2c1-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="1e2c1-104">Технология NewTek NDI® (Network Device Interface) — это современное решение для подключения медиа устройств (например, студийной камеры и mixer).</span><span class="sxs-lookup"><span data-stu-id="1e2c1-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="1e2c1-105">Вместо физических подключений технология NDI® обеспечивает подключение к локальной интрасети, в том числе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="1e2c1-106">Технология NDI® стала стандартным отраслевым решением для создания трансляций контента для потоков и стала более заметной в профессиональном мире широковещательного бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="1e2c1-107">Ранее Skype добавил функции ® NDI в Skype в конце 2018 г.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="1e2c1-108">Microsoft Teams использует эти функции для улучшения проведения собраний.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="1e2c1-109">Технология NDI® ограничена локальной сетью и должна рассматриваться только как часть рабочего процесса, а не решения для трансляции.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="1e2c1-110">Включив технологию NDI®</span><span class="sxs-lookup"><span data-stu-id="1e2c1-110">Turn on NDI® technology</span></span>

<span data-ttu-id="1e2c1-111">Для ® NDI требуется два шага для того, чтобы пользователь включил ее.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="1e2c1-112">Администратор клиента должен включить свойство AllowNDIStreaming в CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="1e2c1-113">После заполнения этого изменения конечный пользователь должен включить технологию NDI® для своего клиента в **параметрах**  >  **разрешений.**</span><span class="sxs-lookup"><span data-stu-id="1e2c1-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="1e2c1-114">Когда пользователь присоединяется к собранию, он видит сообщение о том, что собрание транслируется.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="1e2c1-115">Если пользователи не хотят включаться в трансляцию, им нужно будет отойди от собрания.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="1e2c1-116">На следующем рисунке показано сообщение баннера, которое пользователь видит на собрании Teams.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![He NDI® technology banner that displays in a Teams meeting.](media/NDI-disclosure.png)

<span data-ttu-id="1e2c1-118">Баннер имеет ссылку на политику [конфиденциальности Майкрософт.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="1e2c1-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="1e2c1-119">Поддерживаемые региональные и пользовательские типы</span><span class="sxs-lookup"><span data-stu-id="1e2c1-119">Supported locales and user types</span></span>

<span data-ttu-id="1e2c1-120">NDI® поддерживается во всех региональных сфере.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="1e2c1-121">В поток NDI® NDI включаются следующие пользователи, но не все они могут получить доступ к ® NDI:</span><span class="sxs-lookup"><span data-stu-id="1e2c1-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="1e2c1-122">Клиент — полная поддержка, которая доставляется на основе ring/tenantId/userId (управляется политикой собраний)</span><span class="sxs-lookup"><span data-stu-id="1e2c1-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="1e2c1-123">Федерательный — без потокового доступа (даже если ® NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1e2c1-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="1e2c1-124">Premium — без потокового доступа</span><span class="sxs-lookup"><span data-stu-id="1e2c1-124">Premium - no stream access</span></span>
- <span data-ttu-id="1e2c1-125">Анонимный доступ — нет потокового доступа</span><span class="sxs-lookup"><span data-stu-id="1e2c1-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="1e2c1-126">Гость — нет потокового доступа</span><span class="sxs-lookup"><span data-stu-id="1e2c1-126">Guest – no stream access</span></span>  

<span data-ttu-id="1e2c1-127"><sup>На 1</sup> устройствах есть ® NDI, которая по умолчанию находится в режиме NDI.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="1e2c1-128">Если участник собрания использует устройство с выключенной технологией NDI®, он должен включить ® NDI.</span><span class="sxs-lookup"><span data-stu-id="1e2c1-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
