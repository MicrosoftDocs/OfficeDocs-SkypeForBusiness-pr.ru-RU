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
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598468"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="0f39f-103">Использование технологии NDI® в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f39f-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="0f39f-104">Технология NewNdi® (интерфейс сетевого устройства) — это современное решение для подключения устройств мультимедиа (например, камеры studio и миксера).</span><span class="sxs-lookup"><span data-stu-id="0f39f-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="0f39f-105">Вместо физических подключений технология NDI® обеспечивает подключение к локальной интрасети, в том числе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f39f-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="0f39f-106">Технология NDI® стала стандартным отраслевым решением для создания трансляции содержимого для потоков и стала заметной в мире профессионального широковещательного канала.</span><span class="sxs-lookup"><span data-stu-id="0f39f-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="0f39f-107">Skype в конце 2018 г. ® функции Skype NDI.</span><span class="sxs-lookup"><span data-stu-id="0f39f-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="0f39f-108">Microsoft Teams эту функцию можно использовать для улучшения работы с собраниями.</span><span class="sxs-lookup"><span data-stu-id="0f39f-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="0f39f-109">NDI® технология ограничена локальной сетью и должна рассматриваться только как часть рабочего процесса, а не широковещательного решения.</span><span class="sxs-lookup"><span data-stu-id="0f39f-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="0f39f-110">Включите технологию NDI®</span><span class="sxs-lookup"><span data-stu-id="0f39f-110">Turn on NDI® technology</span></span>

<span data-ttu-id="0f39f-111">Для ® NDI требуется два этапа.</span><span class="sxs-lookup"><span data-stu-id="0f39f-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="0f39f-112">Администратор клиента должен включить свойство AllowNDIStreaming в CsTeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0f39f-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="0f39f-113">После заполнения этого изменения конечный пользователь должен включить технологию NDI® для своего клиента из **Параметры**  >  **разрешений.**</span><span class="sxs-lookup"><span data-stu-id="0f39f-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="0f39f-114">Когда пользователь присоединяется к собранию, он видит сообщение о том, что собрание транслируется.</span><span class="sxs-lookup"><span data-stu-id="0f39f-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="0f39f-115">Если пользователи не хотят включаться в трансляцию, им нужно будет отказаться от собрания.</span><span class="sxs-lookup"><span data-stu-id="0f39f-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="0f39f-116">На рисунке ниже показано баннерное сообщение, которое пользователь видит на Teams собрании.</span><span class="sxs-lookup"><span data-stu-id="0f39f-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![He NDI® technology banner that displays in a Teams meeting.](media/NDI-disclosure.png)

<span data-ttu-id="0f39f-118">Баннер имеет ссылку на политику [конфиденциальности Майкрософт.](https://aka.ms/teamsprivacy)</span><span class="sxs-lookup"><span data-stu-id="0f39f-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="0f39f-119">NDI® активируется только в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="0f39f-119">NDI® is activated per session only.</span></span> <span data-ttu-id="0f39f-120">При следующем входе пользователь должен активировать его перед использованием NDI®.</span><span class="sxs-lookup"><span data-stu-id="0f39f-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="0f39f-121">Поддерживаемые региональные и пользовательские типы</span><span class="sxs-lookup"><span data-stu-id="0f39f-121">Supported locales and user types</span></span>

<span data-ttu-id="0f39f-122">NDI® поддерживается во всех региональных.</span><span class="sxs-lookup"><span data-stu-id="0f39f-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="0f39f-123">Следующие пользователи включаются в поток NDI® технологий, но не все пользователи могут получить доступ к ® NDI:</span><span class="sxs-lookup"><span data-stu-id="0f39f-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="0f39f-124">In-tenant — полная поддержка, которая была доставлена на основе ring/tenantId/userId (управляется политикой собраний)</span><span class="sxs-lookup"><span data-stu-id="0f39f-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="0f39f-125">Федерательная : без потокового доступа (даже если ® NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0f39f-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="0f39f-126">Premium — нет потокового доступа</span><span class="sxs-lookup"><span data-stu-id="0f39f-126">Premium - no stream access</span></span>
- <span data-ttu-id="0f39f-127">Анонимный доступ без потокового доступа</span><span class="sxs-lookup"><span data-stu-id="0f39f-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="0f39f-128">Гостевой доступ — без потокового доступа</span><span class="sxs-lookup"><span data-stu-id="0f39f-128">Guest – no stream access</span></span>  

<span data-ttu-id="0f39f-129"><sup>1</sup> Устройства имеют параметр ® NDI, который по умолчанию находится в режиме NDI.</span><span class="sxs-lookup"><span data-stu-id="0f39f-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="0f39f-130">Если участник собрания использует устройство с выключенной технологией NDI®, он должен включить ® NDI.</span><span class="sxs-lookup"><span data-stu-id="0f39f-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
