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
description: Сведения о том, как использовать NDI в Microsoft Teams.
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
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="57b85-103">Использование NDI® технологии в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57b85-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="57b85-104">NewTek NDI® (интерфейс сетевого устройства) — это современное решение для подключения устройств мультимедиа (например, камеры и микшера).</span><span class="sxs-lookup"><span data-stu-id="57b85-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="57b85-105">Вместо использования физических подключений технология NDI® обеспечивает подключение через локальную интрасеть, в том числе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="57b85-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="57b85-106">Технология NDI® стала стандартным отраслевым решением для создания живого содержимого для потоков и получения важной информации и внедрения в профессиональном эфирном мире.</span><span class="sxs-lookup"><span data-stu-id="57b85-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="57b85-107">Ранее в 2018® NDI функция Skype была добавлена в Skype.</span><span class="sxs-lookup"><span data-stu-id="57b85-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="57b85-108">Microsoft Teams использует эти функции для повышения эффективности собраний.</span><span class="sxs-lookup"><span data-stu-id="57b85-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="57b85-109">Технология NDI® ограничена в локальной сети, и ее можно считать только частью рабочего процесса, а не широковещательным решением.</span><span class="sxs-lookup"><span data-stu-id="57b85-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="57b85-110">Включение технологии NDI®</span><span class="sxs-lookup"><span data-stu-id="57b85-110">Turn on NDI® technology</span></span>

<span data-ttu-id="57b85-111">Для использования технологии NDI® требуется два действия, которые необходимо включить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="57b85-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="57b85-112">Администратор клиента должен включить свойство "AllowNDIStreaming" в CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="57b85-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="57b85-113">После того как это изменение будет заполнено, конечный пользователь должен включить NDI® технологии для определенного клиента из разрешений на **Параметры**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="57b85-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="57b85-114">Когда пользователь присоединяется к собранию, он увидит сообщение с уведомлением о том, что собрание пересылается.</span><span class="sxs-lookup"><span data-stu-id="57b85-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="57b85-115">Если вы не хотите, чтобы пользователи были включены в вещание, они должны будут перетаскиваться с собрания.</span><span class="sxs-lookup"><span data-stu-id="57b85-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="57b85-116">На приведенном ниже рисунке показано сообщение с рекламой, которое пользователь видит в собрании Teams.</span><span class="sxs-lookup"><span data-stu-id="57b85-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Он NDI®ный плакат, который отображается в собрании Teams.](media/NDI-disclosure.png)

<span data-ttu-id="57b85-118">Баннер содержит ссылку на [политику конфиденциальности Майкрософт](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="57b85-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="57b85-119">Поддерживаемые национальные настройки и пользовательские типы</span><span class="sxs-lookup"><span data-stu-id="57b85-119">Supported locales and user types</span></span>

<span data-ttu-id="57b85-120">Технология NDI® поддерживается всеми языками.</span><span class="sxs-lookup"><span data-stu-id="57b85-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="57b85-121">Следующие пользователи включены в поток технологии NDI®, но не все пользователи могут получить доступ к потоку технологии NDI®:</span><span class="sxs-lookup"><span data-stu-id="57b85-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="57b85-122">Полная поддержка в клиенте, Доставка которой осуществляется на основе звонков/tenantId/userId (в соответствии с политикой собраний).</span><span class="sxs-lookup"><span data-stu-id="57b85-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="57b85-123">Федеративная — нет доступа к потоку (даже если у них есть технология NDI®)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="57b85-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="57b85-124">Premium — нет доступа к потоку</span><span class="sxs-lookup"><span data-stu-id="57b85-124">Premium - no stream access</span></span>
- <span data-ttu-id="57b85-125">Анонимный – нет доступа к потоку</span><span class="sxs-lookup"><span data-stu-id="57b85-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="57b85-126">Гость — нет доступа к потоку</span><span class="sxs-lookup"><span data-stu-id="57b85-126">Guest – no stream access</span></span>  

<span data-ttu-id="57b85-127">у <sup>1</sup> устройств есть параметр технологии NDI®, который используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="57b85-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="57b85-128">Если участник собрания использует устройство с NDI® технологиями, им потребуется включить NDIную технологию®.</span><span class="sxs-lookup"><span data-stu-id="57b85-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
