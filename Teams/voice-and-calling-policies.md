---
title: Управление политиками голосовой и голосовой почты в Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2021
ms.locfileid: "50348094"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="c3fad-102">Управление политиками голосовой и голосовой почты в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3fad-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="c3fad-103">Политики голосовых и звонков используются для управления голосовой и голосовой почтой в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3fad-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="c3fad-104">Политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="c3fad-104">Emergency calling policies</span></span>

<span data-ttu-id="c3fad-105">Политики [экстренных вызовов](manage-emergency-calling-policies.md) используются для настройки того, что происходит, когда пользователь в вашей организации звонит.</span><span class="sxs-lookup"><span data-stu-id="c3fad-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="c3fad-106">Эти политики управляются в Центре администрирования Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3fad-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![Снимок экрана: политика для экстренных вызовов.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="c3fad-108">Политики маршрутинга экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="c3fad-108">Emergency call routing policies</span></span>

<span data-ttu-id="c3fad-109">Если в вашей организации развернута прямая маршрутия [](manage-emergency-call-routing-policies.md) телефонной **системы,** вы можете использовать политики маршрутизации экстренных вызовов, чтобы определить, куда перенаправят экстренные вызовы, включены ли улучшенные экстренные службы и какие номера используются для экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="c3fad-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="c3fad-110">Управление этими политиками можно с помощью PowerShell или Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3fad-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![Снимок экрана: политика маршрутинга экстренных вызовов.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="c3fad-112">Политики ИД вызываемой вызовы</span><span class="sxs-lookup"><span data-stu-id="c3fad-112">Caller ID policies</span></span>

<span data-ttu-id="c3fad-113">[Политики, используемые для изменения](caller-id-policies.md) или блокировки этих политик, применяются для их изменения.</span><span class="sxs-lookup"><span data-stu-id="c3fad-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![Снимок экрана: политика "ИД звоня"](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="c3fad-115">Политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="c3fad-115">Voice routing policies</span></span>

<span data-ttu-id="c3fad-116">Политика [голосовой маршрутки —](manage-voice-routing-policies.md) это контейнер для записей об использовании телефонной сети общего пользования (ННР).</span><span class="sxs-lookup"><span data-stu-id="c3fad-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="c3fad-117">Эти политики можно использовать, если в вашей организации развернута прямая маршрутия телефонной **системы.**</span><span class="sxs-lookup"><span data-stu-id="c3fad-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="c3fad-118">Для управления политиками маршрутинга голосовой связи можно использовать PowerShell или Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="c3fad-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![Снимок экрана: политика маршрутинга голосовой почты.](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="c3fad-120">Политики звонков</span><span class="sxs-lookup"><span data-stu-id="c3fad-120">Calling policies</span></span>

<span data-ttu-id="c3fad-121">[Политики звонков](teams-calling-policy.md) контролируют, какие функции переад управление звонками и переад управлением звонками доступны пользователям, включая возможность частных звонков, отправки звонков в группы звонков и перенаправка звонков на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="c3fad-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![Снимок экрана: политика звонков.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="c3fad-123">Парковка вызовов и извлечение политик</span><span class="sxs-lookup"><span data-stu-id="c3fad-123">Call park and retrieve policies</span></span>

<span data-ttu-id="c3fad-124">[Если сделать это,](call-park-and-retrieve.md) другие пользователи будут поставлены на удержание и смогут продолжать звонок тому же или другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="c3fad-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![Снимок экрана: парк вызовов и извлечение политики.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="c3fad-126">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="c3fad-126">Create and manage dial plans</span></span>

<span data-ttu-id="c3fad-127">[В наборах](create-and-manage-dial-plans.md) можно переводить номера телефонов для авторизации и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="c3fad-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="c3fad-128">Создавать наборные группы и управлять ими можно с помощью PowerShell или Центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3fad-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![Снимок экрана: набор номеров.](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="c3fad-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c3fad-130">Related topics</span></span>

* [<span data-ttu-id="c3fad-131">Управление политиками экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3fad-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="c3fad-132">Управление политиками маршрутизации экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="c3fad-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="c3fad-133">Управление политиками ИД звоня в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3fad-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="c3fad-134">Управление политиками маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="c3fad-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="c3fad-135">Политики звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3fad-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="c3fad-136">Парковка и восстановление звонков в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3fad-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="c3fad-137">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="c3fad-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="c3fad-138">Управление командами с помощью политик</span><span class="sxs-lookup"><span data-stu-id="c3fad-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
