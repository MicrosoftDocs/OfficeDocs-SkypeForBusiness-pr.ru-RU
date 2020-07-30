---
title: Помощник по голосовым сообщениям кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Сведения об использовании голосового помощника Кортаны с командами
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522325"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="7b0ef-103">Помощь по голосовой связи кортаны в Teams</span><span class="sxs-lookup"><span data-stu-id="7b0ef-103">Cortana voice assistance in Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> <span data-ttu-id="7b0ef-104">Поддержка голосовой почты кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android только для пользователей из Соединенных Штатов.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="7b0ef-105">В настоящее время она недоступна для клиентов GCC, GCC-High, DoD, и для них.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="7b0ef-106">В будущих выпусках будут вычислены дополнительные языки и регионы.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="7b0ef-107">Голосовая служба кортаны в мобильном приложении Teams позволяет пользователям Microsoft 365 предприятия ускорить взаимодействие, совместную работу и задачи, связанные с собраниями, с помощью голосового языка.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="7b0ef-108">Пользователи могут поговорить с Кортаной, нажав кнопку микрофона, расположенную в правом верхнем углу приложения Teams Mobile.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="7b0ef-109">Чтобы быстро подключаться к группе в пути, пользователи могут сказать запросы, например "позвонить Megan" или "отправить сообщение на мое приглашение на собрание".</span><span class="sxs-lookup"><span data-stu-id="7b0ef-109">To quickly connect with their team while on the go, users can say queries such as “call Megan” or “send a message to my next meeting.”</span></span> <span data-ttu-id="7b0ef-110">Пользователи также могут присоединяться к собраниям, нажимая "присоединиться к следующему собранию", и использовать голосовую помощь для предоставления доступа к файлам, проверки календаря и других возможностей.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-110">Users can also join meetings by saying “join my next meeting” and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="7b0ef-111">Эти возможности голосовой связи доставляются с использованием [служб кортаны Enterprise](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) , которые полностью соответствуют требованиям к конфиденциальности, безопасности и соблюдению требований в Office 365 в [терминах Интернет-служб (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="7b0ef-112">На этом рисунке показано, как отправить чат в Кортана на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![На рисунке показана последовательность на мобильных экранах с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="7b0ef-114">Элементы управления администрированием и ограничениями</span><span class="sxs-lookup"><span data-stu-id="7b0ef-114">Admin control and Limitations</span></span>

<span data-ttu-id="7b0ef-115">Помощь по голосовой связи кортаны в Teams осуществляется с помощью служб, которые полностью соответствуют требованиям Office 365, а также о том, как это было отражено в терминах Интернет-служб (OST).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="7b0ef-116">Эта функция будет включена по умолчанию для клиентов.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="7b0ef-117">Администраторы клиентов могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="7b0ef-118">Этот параметр политики можно задать либо на уровне учетной записи пользователя, либо в клиенте.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="7b0ef-119">Администраторы могут использовать поле CortanaVoiceInvocationMode в рамках этого элемента управления политики, чтобы определить, отключено ли Кортана, включено с помощью кнопки "Отправить", а также с вызовом Word (применимо к устройствам, поддерживающим эту функцию).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="7b0ef-120">Администраторы могут использовать следующие командлеты PowerShell для управления этой политикой (в настоящее время эта политика недоступна в центре администрирования Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="7b0ef-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="7b0ef-121">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7b0ef-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7b0ef-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7b0ef-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7b0ef-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7b0ef-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7b0ef-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7b0ef-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7b0ef-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7b0ef-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="7b0ef-126">Например, в приведенной ниже команде создается новая политика с именем "EmployeeCortanaPolicy", в которой отключен голосовой помощник Кортаны в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-126">For example, the command below creates a new policy with name "EmployeeCortanaPolicy" where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="7b0ef-127">В этом примере показано, как обновить существующую политику с именем "EmployeeCortanaPolicy" и включить голосовой помощник Кортаны в Microsoft Teams с помощью кнопки "Отправить".</span><span class="sxs-lookup"><span data-stu-id="7b0ef-127">This example shows updating an existing policy with name "EmployeeCortanaPolicy" and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="7b0ef-128">Пользователи смогут вызвать Кортана, нажав на кнопку "микрофон Кортаны" в Teams.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="7b0ef-129">Вызов функции пробуждения Word (Привет, Кортана!) будет отключен.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-129">Wake word ("Hey Cortana”) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="7b0ef-130">В этом примере показано, как обновить политику и включить голосовой помощник Кортаны с помощью кнопки и вызова пробуждения по словам.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="7b0ef-131">На момент первоначального выпуска для пользователей Microsoft 365 Enterprise в США на английском языке приложение Teams не будет поддерживать функцию активации Word, но будет поддерживаться в будущем.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="7b0ef-132">Пользовательский элемент управления</span><span class="sxs-lookup"><span data-stu-id="7b0ef-132">User control</span></span>

<span data-ttu-id="7b0ef-133">Отдельные пользователи могут опробовать голосовую справку Кортаны в мобильном приложении Teams, нажав кнопку "микрофон".</span><span class="sxs-lookup"><span data-stu-id="7b0ef-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="7b0ef-134">Кроме того, они могут управлять включением Кортаны в Teams для устройства с помощью параметра в мобильном приложении Teams.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="7b0ef-135">Откройте мобильное приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="7b0ef-136">Перейдите в раздел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="7b0ef-137">Выберите **Кортана**.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="7b0ef-138">Установите переключатель в положение **вкл** . **, в**зависимости от того, хотите ли вы использовать голосовую поддержку кортаны на устройстве.</span><span class="sxs-lookup"><span data-stu-id="7b0ef-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
