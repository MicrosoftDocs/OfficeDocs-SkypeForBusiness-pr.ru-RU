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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588293"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="7e7b7-103">Использование NDI в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e7b7-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="7e7b7-104">Интерфейс сетевых устройств (NDI) — это современное решение для подключения устройств мультимедиа (например, камеры и микшера Studio).</span><span class="sxs-lookup"><span data-stu-id="7e7b7-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="7e7b7-105">Вместо использования физических подключений NDI включает подключение через локальную интрасеть, в том числе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="7e7b7-106">NewTek NDI® стала стандартным отраслевым решением для создания живого содержимого для потоков и значительной осведомленности и внедрения в мир широковещательных кадров профессионального качества.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="7e7b7-107">Ранее вы добавили в Skype 2018 функцию NDI.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="7e7b7-108">Microsoft Teams использует эти функции для повышения эффективности собраний.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="7e7b7-109">NDI ограничен в локальной сети, и его следует считать только частью рабочего процесса, а не широковещательным решением.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="7e7b7-110">Включение NDI</span><span class="sxs-lookup"><span data-stu-id="7e7b7-110">Turn on NDI</span></span>

<span data-ttu-id="7e7b7-111">NDI требует, чтобы пользователь включил два действия.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="7e7b7-112">Администратор клиента должен включить свойство "AllowNDIStreaming" в CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="7e7b7-113">После того как это изменение будет заполнено, конечный пользователь должен включить NDI для определенного клиента из разрешений на **Параметры**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="7e7b7-114">Когда пользователь присоединяется к собранию, он увидит сообщение с уведомлением о том, что собрание пересылается.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="7e7b7-115">Если вы не хотите, чтобы пользователи были включены в вещание, они должны будут перетаскиваться с собрания.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="7e7b7-116">На приведенном ниже рисунке показано сообщение с рекламой, которое пользователь видит в собрании Teams.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Изображение баннера NDI, которое отображается в собрании Teams.](media/NDI-disclosure.png)

<span data-ttu-id="7e7b7-118">Баннер содержит ссылку на [политику конфиденциальности Майкрософт](https://aka.ms/teamsprivacy).</span><span class="sxs-lookup"><span data-stu-id="7e7b7-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="7e7b7-119">Поддерживаемые национальные настройки и пользовательские типы</span><span class="sxs-lookup"><span data-stu-id="7e7b7-119">Supported locales and user types</span></span>

<span data-ttu-id="7e7b7-120">NDI поддерживается всеми языками.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-120">NDI is supported in all locales.</span></span> <span data-ttu-id="7e7b7-121">В собрании NDI поддерживаются следующие пользователи:</span><span class="sxs-lookup"><span data-stu-id="7e7b7-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="7e7b7-122">Полная поддержка в клиенте, Доставка которой осуществляется на основе звонков/tenantId/userId (в соответствии с политикой собраний).</span><span class="sxs-lookup"><span data-stu-id="7e7b7-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="7e7b7-123">Федеративная – нет (даже если у них NDI на)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7e7b7-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="7e7b7-124">Freemium-No (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7e7b7-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="7e7b7-125">Анонимный – нет (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7e7b7-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="7e7b7-126">Гость – нет (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7e7b7-126">Guest – no  (default value)</span></span>

<span data-ttu-id="7e7b7-127">по умолчанию для <sup>1</sup> устройств ЗАДАН параметр NDI.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="7e7b7-128">Если участник собрания использует устройство с NDI, необходимо включить NDI.</span><span class="sxs-lookup"><span data-stu-id="7e7b7-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
