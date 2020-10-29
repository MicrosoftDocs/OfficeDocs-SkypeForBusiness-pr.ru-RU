---
title: Помощь по голосовой связи кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Инструкции по использованию голосовой поддержки Кортаны в Teams
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785393"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="f5969-103">Помощь по голосовой связи кортаны в Teams</span><span class="sxs-lookup"><span data-stu-id="f5969-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="f5969-104">Поддержка голосовой почты кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android, а в Microsoft Teams — только для пользователей из Соединенных Штатов.</span><span class="sxs-lookup"><span data-stu-id="f5969-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="f5969-105">В настоящее время она недоступна для клиентов GCC, GCC-High, DoD, и для них.</span><span class="sxs-lookup"><span data-stu-id="f5969-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="f5969-106">В будущих выпусках будут вычислены дополнительные языки и регионы.</span><span class="sxs-lookup"><span data-stu-id="f5969-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="f5969-107">Голосовая помощь кортаны в приложении Teams и на устройствах отображения в Microsoft Teams позволяет пользователям Microsoft 365 предприятия ускорить взаимодействие, совместную работу и задачи, связанные с собраниями, с помощью голосового языка.</span><span class="sxs-lookup"><span data-stu-id="f5969-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="f5969-108">Пользователи могут говорить с Кортаной, выбирая кнопку микрофона, расположенную в правом верхнем углу приложения Teams, или произнося &#8220;Кортаны&#8221; на экране Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5969-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="f5969-109">Чтобы быстро подключаться с помощью своей команды и во время работы, пользователи могут сказать такие запросы, как &#8220;позвонить Megan&#8221; или &#8220;отправить сообщение на свое следующее собрание&#8221;.</span><span class="sxs-lookup"><span data-stu-id="f5969-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="f5969-110">Пользователи также могут присоединяться к собраниям, выполняя &#8220;присоединиться к следующему собранию&#8221; и выполнив помощь по голосовой связи для совместного использования файлов, проверки календаря и других возможностей.</span><span class="sxs-lookup"><span data-stu-id="f5969-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="f5969-111">Эти возможности голосовой связи доставляются с использованием [служб кортаны Enterprise](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) , которые полностью соответствуют требованиям к конфиденциальности, безопасности и соблюдению требований в Office 365 в [терминах Интернет-служб (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="f5969-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="f5969-112">На этом рисунке показано, как отправить чат с помощью Кортаны на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5969-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![На рисунке показана последовательность на мобильных экранах с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="f5969-114">Элементы управления администрированием и ограничениями</span><span class="sxs-lookup"><span data-stu-id="f5969-114">Admin control and limitations</span></span>

<span data-ttu-id="f5969-115">Помощь по голосовой связи кортаны в Teams осуществляется с помощью служб, которые полностью соответствуют требованиям Office 365, а также о том, как это было отражено в терминах Интернет-служб (OST).</span><span class="sxs-lookup"><span data-stu-id="f5969-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="f5969-116">Эта функция будет включена по умолчанию для клиентов.</span><span class="sxs-lookup"><span data-stu-id="f5969-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="f5969-117">Администраторы клиентов могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="f5969-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="f5969-118">Этот параметр политики можно задать либо на уровне учетной записи пользователя, либо в клиенте.</span><span class="sxs-lookup"><span data-stu-id="f5969-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="f5969-119">Администраторы могут использовать поле CortanaVoiceInvocationMode в этом элементе управления политики, чтобы определить, отключено ли Кортана, включить с помощью кнопки "Отправить", а также использовать вызов Word (применимо только к устройствам, поддерживающим эту функцию, например в Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="f5969-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="f5969-120">Администраторы могут использовать следующие командлеты PowerShell для управления этой политикой (в настоящее время эта политика недоступна в центре администрирования Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="f5969-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="f5969-121">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f5969-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f5969-122">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f5969-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f5969-123">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f5969-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f5969-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f5969-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f5969-125">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f5969-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="f5969-126">Например, приведенная ниже команда создает новую политику с именем &#8220;EmployeeCortanaPolicy&#8221;, в которой служба поддержки голосовой связи Кортаны в Microsoft Teams отключена.</span><span class="sxs-lookup"><span data-stu-id="f5969-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="f5969-127">В этом примере показано обновление существующей политики с именем &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой поддержки Кортаны в Microsoft Teams с помощью кнопки "Отправить".</span><span class="sxs-lookup"><span data-stu-id="f5969-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="f5969-128">Пользователи смогут вызвать Кортана, нажав кнопку "микрофон Кортаны" в Teams.</span><span class="sxs-lookup"><span data-stu-id="f5969-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="f5969-129">Вызов функции пробуждения Word (&#8220;Привет, Кортана&#8221; или &#8220;Кортаны&#8221;) будет отключена.</span><span class="sxs-lookup"><span data-stu-id="f5969-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="f5969-130">В этом примере показано, как обновить политику и включить голосовую помощь Кортаны с помощью кнопки и вызова пробуждения по словам.</span><span class="sxs-lookup"><span data-stu-id="f5969-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="f5969-131">На момент первоначального выпуска для пользователей Microsoft 365 Enterprise в США на английском языке приложение Teams не будет поддерживать функцию активации Word, но будет поддерживаться в будущем.</span><span class="sxs-lookup"><span data-stu-id="f5969-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="f5969-132">Активация Word в автономном выпуске будет работать на устройствах с интерфейсом Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5969-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="f5969-133">Пользовательский элемент управления</span><span class="sxs-lookup"><span data-stu-id="f5969-133">User control</span></span>

<span data-ttu-id="f5969-134">Отдельные пользователи могут опробовать голосовую справку Кортаны в мобильном приложении Teams, нажав кнопку "микрофон".</span><span class="sxs-lookup"><span data-stu-id="f5969-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="f5969-135">Они могут попытаться использовать голосовые команды Кортаны в Microsoft Teams, просто произнося &#8220;Кортану. &#8221; они также могут управлять включением Кортаны в Teams для устройства с помощью параметра в мобильном приложении Teams или на экране Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5969-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="f5969-136">Откройте мобильное приложение Teams или перейдите на экран внешний вид экрана в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5969-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="f5969-137">В мобильном приложении Teams перейдите в раздел **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="f5969-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="f5969-138">На экране Microsoft Teams выберите аватар пользователя и нажмите кнопку Параметры.</span><span class="sxs-lookup"><span data-stu-id="f5969-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="f5969-139">Если Кортана включена, скажем, &#8220;Кортана, перейдите к разделу Параметры. &#8221;</span><span class="sxs-lookup"><span data-stu-id="f5969-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="f5969-140">Выберите **Кортана** .</span><span class="sxs-lookup"><span data-stu-id="f5969-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="f5969-141">Установите переключатель в положение **вкл** . **, в** зависимости от того, хотите ли вы использовать голосовую поддержку кортаны на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f5969-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
