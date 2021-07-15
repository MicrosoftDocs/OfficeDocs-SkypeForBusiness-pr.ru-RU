---
title: Кортана голосовой помощи в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Узнайте, как использовать Кортана голосовой помощи Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428215"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="a6247-103">Кортана голосовой помощи в Teams</span><span class="sxs-lookup"><span data-stu-id="a6247-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="a6247-104">Кортана поддерживается в мобильных приложениях Microsoft Teams для iOS и Android и Microsoft Teams для пользователей в США, Соединенном Королевстве, Канаде, Индии и Австралии.</span><span class="sxs-lookup"><span data-stu-id="a6247-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="a6247-105">Комнаты Microsoft Teams на Windows поддерживается только для пользователей в США.</span><span class="sxs-lookup"><span data-stu-id="a6247-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="a6247-106">Кортана в настоящее время голосовая помощь недоступна для клиентов GCC, GCC high, DoD и других клиентов EDU.</span><span class="sxs-lookup"><span data-stu-id="a6247-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="a6247-107">Кортана голосовая помощь в мобильном приложении Teams теперь доступна для клиентов в EDU в США.</span><span class="sxs-lookup"><span data-stu-id="a6247-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="a6247-108">Расширение до дополнительных языков и регионов будет происходить в рамках будущих выпусков.</span><span class="sxs-lookup"><span data-stu-id="a6247-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="a6247-109">Кортана голосовая помощь в Комнаты Microsoft Teams выпущена в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="a6247-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="a6247-110">В предварительной версии Кортана поддерживаются только в США на устройствах с подключенными микрофонами Microphone.</span><span class="sxs-lookup"><span data-stu-id="a6247-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="a6247-111">Кортана голосовой помощи в мобильном приложении Teams, в Комнаты Microsoft Teams в Windows и на устройствах Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи.</span><span class="sxs-lookup"><span data-stu-id="a6247-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="a6247-112">Пользователи могут говорить Кортана с помощью кнопки микрофона, расположенной в правом верхнем месте мобильного приложения Teams, или &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании Microsoft Teams экрана.</span><span class="sxs-lookup"><span data-stu-id="a6247-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="a6247-113">Чтобы быстро общаться с командой, находясь в путь, пользователи могут отправлять запросы, например &#8220;позвонить&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;.</span><span class="sxs-lookup"><span data-stu-id="a6247-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="a6247-114">Пользователи также могут присоединяться к собраниям, &#8220;присоединиться к следующему собранию&#8221; и использовать голосовую помощь для обмена файлами, проверки календаря и многого другого.</span><span class="sxs-lookup"><span data-stu-id="a6247-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="a6247-115">Эти голосовые помощники оказания Кортана корпоративного уровня, которые полностью соответствуют Office 365 конфиденциальности, безопасности и соблюдению требований, указанных в Условиях [онлайн-сервисов](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="a6247-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="a6247-116">Управление администратором и ограничения</span><span class="sxs-lookup"><span data-stu-id="a6247-116">Admin control and limitations</span></span>

<span data-ttu-id="a6247-117">Кортана голосовая помощь в Teams выполняется с помощью служб, которые полностью соответствуют требованиям Office 365 конфиденциальности, безопасности и соответствия требованиям на уровне предприятия, как отражено в Условиях онлайн-услуг (OST).</span><span class="sxs-lookup"><span data-stu-id="a6247-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="a6247-118">Эта функция будет включена по умолчанию для клиентов.</span><span class="sxs-lookup"><span data-stu-id="a6247-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="a6247-119">Администраторы клиентов могут управлять тем, кто в своем клиенте может Кортана голосовую помощь Teams с помощью политики (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="a6247-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="a6247-120">Эта политика задается на уровне учетной записи пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="a6247-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="a6247-121">Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли только нажатие кнопки вызова или включено ли оно (применимо к устройствам, которые его поддерживают, например Microsoft Teams дисплею).</span><span class="sxs-lookup"><span data-stu-id="a6247-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="a6247-122">Для управления этой политикой администраторы могут использовать следующие Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6247-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="a6247-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a6247-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a6247-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a6247-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a6247-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a6247-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a6247-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a6247-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="a6247-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="a6247-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="a6247-128">Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где Кортана голосовая помощь в Microsoft Teams отключена.</span><span class="sxs-lookup"><span data-stu-id="a6247-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="a6247-129">В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение Кортана голосовой помощи в Microsoft Teams с помощью push-кнопки вызова.</span><span class="sxs-lookup"><span data-stu-id="a6247-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="a6247-130">Пользователи смогут вызывать Кортана, нажатием кнопки Кортана микрофона в Teams.</span><span class="sxs-lookup"><span data-stu-id="a6247-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="a6247-131">Вывести слово на &#8220;отключено Кортана&#8221; или &#8220;Кортана&#8221;)</span><span class="sxs-lookup"><span data-stu-id="a6247-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="a6247-132">В этом примере показано обновление политики и включение Кортана голосовой помощи с помощью push-кнопки и вызова слова.</span><span class="sxs-lookup"><span data-stu-id="a6247-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="a6247-133">На момент первоначального выпуска для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:</span><span class="sxs-lookup"><span data-stu-id="a6247-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="a6247-134">Мобильное Teams не поддерживает активацию word, но в будущем оно будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="a6247-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="a6247-135">Комнаты Microsoft Teams на Windows и Microsoft Teams поддерживают активацию word.</span><span class="sxs-lookup"><span data-stu-id="a6247-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="a6247-136">Пользовательский контроль</span><span class="sxs-lookup"><span data-stu-id="a6247-136">User control</span></span>

<span data-ttu-id="a6247-137">Отдельные пользователи могут попробовать Кортана голосовой помощи на разных устройствах:</span><span class="sxs-lookup"><span data-stu-id="a6247-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="a6247-138">В мобильном приложении Teams кнопку микрофона.</span><span class="sxs-lookup"><span data-stu-id="a6247-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="a6247-139">Выберите кнопку микрофона или скажите "Кортана" в Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a6247-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="a6247-140">Скажите "Кортана" на Microsoft Teams отображает устройства.</span><span class="sxs-lookup"><span data-stu-id="a6247-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="a6247-141">Вы можете включить Кортана в Teams, используя параметр устройства.</span><span class="sxs-lookup"><span data-stu-id="a6247-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="a6247-142">Комнаты Microsoft Teams Windows</span><span class="sxs-lookup"><span data-stu-id="a6247-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="a6247-143">Внесение изменений на уровне устройства Кортана на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="a6247-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="a6247-144">Кортана будет выключено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6247-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="a6247-145">Чтобы Кортана на уровне устройства, эти атрибуты XML должны быть добавлены в XML-файл SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="a6247-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="a6247-146">Внесение изменений на уровне собрания Кортана на уровне устройства.</span><span class="sxs-lookup"><span data-stu-id="a6247-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="a6247-147">Чтобы включить Кортана голосовой помощи во время собрания, переключите или выключите . </span><span class="sxs-lookup"><span data-stu-id="a6247-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="a6247-148">После окончания собрания Кортана к настройкам уровня устройства.</span><span class="sxs-lookup"><span data-stu-id="a6247-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
