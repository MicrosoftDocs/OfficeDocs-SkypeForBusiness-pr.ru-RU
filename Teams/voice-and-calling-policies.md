---
title: Управление политиками голосовой и голосовой Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Узнайте о политиках Teams голосовой и голосовой почты.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460589"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="9f50e-103">Управление политиками голосовой и голосовой Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f50e-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="9f50e-104">Политики голосовой и голосовой почты используются для управления голосовой и голосовой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f50e-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="9f50e-105">Политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="9f50e-105">Emergency calling policies</span></span>

<span data-ttu-id="9f50e-106">Политики [экстренных вызовов](manage-emergency-calling-policies.md) используются для настройки того, что происходит, когда пользователь в вашей организации звонит.</span><span class="sxs-lookup"><span data-stu-id="9f50e-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="9f50e-107">Управление этими политиками можно Teams центре администрирования или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f50e-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Снимок экрана: политика экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="9f50e-109">Политики маршрутизов экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="9f50e-109">Emergency call routing policies</span></span>

<span data-ttu-id="9f50e-110">Если в вашей организации развернута прямая **маршрут телефонная система,** [](manage-emergency-call-routing-policies.md) вы можете использовать политики маршрутизации экстренных вызовов, чтобы определить, куда перенаправят экстренные вызовы, включены ли улучшенные экстренные службы и какие номера используются для экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="9f50e-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="9f50e-111">Управлять этими политиками можно с помощью PowerShell или Microsoft Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9f50e-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Снимок экрана: политика маршрутизов экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="9f50e-113">Политики ИД вызываемой вызовы</span><span class="sxs-lookup"><span data-stu-id="9f50e-113">Caller ID policies</span></span>

<span data-ttu-id="9f50e-114">[Для изменения или блокировки](caller-id-policies.md) ИД вызываемой вызываемой вызовы применяются политики.</span><span class="sxs-lookup"><span data-stu-id="9f50e-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Снимок экрана: политика ИД вызываемого звоня.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="9f50e-116">Политики маршрутов голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="9f50e-116">Voice routing policies</span></span>

<span data-ttu-id="9f50e-117">Политика [голосовой маршрутистики](manage-voice-routing-policies.md) является контейнером для записей использования телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="9f50e-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="9f50e-118">Эти политики можно использовать, если в вашей организации развернута прямая **телефонная система маршрутизации.**</span><span class="sxs-lookup"><span data-stu-id="9f50e-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="9f50e-119">Управление политиками маршрутинга голосовой почты можно управлять с помощью PowerShell или Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9f50e-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Снимок экрана: политика маршрутинга голосовой почты.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="9f50e-121">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="9f50e-121">Calling policies</span></span>

<span data-ttu-id="9f50e-122">[Политики звонков](teams-calling-policy.md) контролируют, какие функции переад сообщения и вызовы доступны пользователям, включая возможность личных звонков, отправки звонков в группы звонков и перенаправка звонков на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="9f50e-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Снимок экрана: политика звонков.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="9f50e-124">Парк вызовов и извлечение политик</span><span class="sxs-lookup"><span data-stu-id="9f50e-124">Call park and retrieve policies</span></span>

<span data-ttu-id="9f50e-125">[Парк вызовов и извлечение](call-park-and-retrieve.md) позволяет пользователям помещать других пользователей на удержание и позволяет тому же пользователю или другому пользователю продолжить звонок.</span><span class="sxs-lookup"><span data-stu-id="9f50e-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Снимок экрана: парк вызовов и извлечение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="9f50e-127">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="9f50e-127">Create and manage dial plans</span></span>

<span data-ttu-id="9f50e-128">[В планах набора](create-and-manage-dial-plans.md) можно переводить номера телефонов для авторизации звонков и маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="9f50e-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="9f50e-129">Вы можете создавать наборные группы и управлять ими с помощью PowerShell или Microsoft Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="9f50e-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Снимок экрана: план набора номера.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="9f50e-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9f50e-131">Related topics</span></span>

* [<span data-ttu-id="9f50e-132">Управление политиками экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f50e-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="9f50e-133">Управление политиками маршрутизации экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="9f50e-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="9f50e-134">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f50e-134">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="9f50e-135">Управление политиками перенаправки голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9f50e-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="9f50e-136">Политики звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f50e-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="9f50e-137">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f50e-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="9f50e-138">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="9f50e-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="9f50e-139">Управление Teams политиками</span><span class="sxs-lookup"><span data-stu-id="9f50e-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
