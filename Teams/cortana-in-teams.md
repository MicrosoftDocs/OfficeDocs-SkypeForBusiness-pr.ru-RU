---
title: Голосовая помощь Кортаны в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: Узнайте, как использовать голосовую помощь Кортаны в Teams
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
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886738"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="b0823-103">Голосовая помощь Кортаны в Teams</span><span class="sxs-lookup"><span data-stu-id="b0823-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="b0823-104">Голосовая помощь Кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android и Microsoft Teams для пользователей в США, Соединенном Королевстве, Канаде, Индии и Австралии.</span><span class="sxs-lookup"><span data-stu-id="b0823-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span>  <span data-ttu-id="b0823-105">Комнаты Microsoft Teams для Windows поддерживаются только пользователями в США.</span><span class="sxs-lookup"><span data-stu-id="b0823-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="b0823-106">Голосовая помощь Кортаны в настоящее время недоступна для клиентов GCC, GCC-High, DoD и EDU.</span><span class="sxs-lookup"><span data-stu-id="b0823-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="b0823-107">Расширение до дополнительных языков и регионов будет происходить в рамках будущих выпусков.</span><span class="sxs-lookup"><span data-stu-id="b0823-107">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="b0823-108">Голосовая помощь Кортаны в комнатах Microsoft Teams выпущена в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="b0823-108">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="b0823-109">В предварительной версии Кортана поддерживается только в США на устройствах, на которые подключены микрофоны Изумительного.</span><span class="sxs-lookup"><span data-stu-id="b0823-109">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="b0823-110">Голосовая помощь Кортаны в мобильном приложении Teams, в комнатах Microsoft Teams для Windows и устройствах отображения Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи.</span><span class="sxs-lookup"><span data-stu-id="b0823-110">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="b0823-111">Пользователи могут говорить с Кортаной, нажав кнопку микрофона в правом верхнем конце мобильного приложения Teams или нажав &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании дисплея Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0823-111">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="b0823-112">Чтобы быстро общаться с командой, находясь в путь, пользователи могут отправлять запросы, например &#8220;позвонить&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;.</span><span class="sxs-lookup"><span data-stu-id="b0823-112">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="b0823-113">Пользователи также могут присоединяться к собраниям, &#8220;присоединиться к следующему собранию&#8221; и использовать голосовую помощь для обмена файлами, проверки календаря и многого другого.</span><span class="sxs-lookup"><span data-stu-id="b0823-113">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="b0823-114">Эти голосовые помощники ставляются с помощью служб корпоративного уровня Кортаны, которые полностью соответствуют требованиям к конфиденциальности, безопасности и соблюдению требований Office 365, как отражено в Условиях [онлайн-услуг](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="b0823-114">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="b0823-115">На изображении показана отправка чата с помощью Кортаны на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="b0823-115">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Последовательность мобильных экранов с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="b0823-117">Управление администратором и ограничения</span><span class="sxs-lookup"><span data-stu-id="b0823-117">Admin control and limitations</span></span>

<span data-ttu-id="b0823-118">Голосовая помощь Кортаны в Teams выполняется с помощью служб, полностью соответствующих требованиям к конфиденциальности, безопасности и соблюдению требований Office 365, которые отражены в Условиях онлайн-услуг (OST).</span><span class="sxs-lookup"><span data-stu-id="b0823-118">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="b0823-119">Эта функция будет включена по умолчанию для клиентов.</span><span class="sxs-lookup"><span data-stu-id="b0823-119">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="b0823-120">Администраторы клиентов могут управлять тем, кто в своем клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="b0823-120">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="b0823-121">Эту политику можно настроить на уровне учетной записи пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="b0823-121">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="b0823-122">Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли она только с помощью кнопки вызова или с отключением слова (применимо к устройствам, которые его поддерживают, например microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="b0823-122">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="b0823-123">Администраторы могут использовать для управления этой политикой следующие командлеты PowerShell (в настоящее время политика недоступна в Центре администрирования Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="b0823-123">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="b0823-124">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b0823-124">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b0823-125">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b0823-125">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b0823-126">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b0823-126">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b0823-127">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b0823-127">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="b0823-128">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="b0823-128">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="b0823-129">Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где голосовая помощь Кортаны в Microsoft Teams отключена.</span><span class="sxs-lookup"><span data-stu-id="b0823-129">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="b0823-130">В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой помощи Кортаны в Microsoft Teams с помощью push-кнопки вызова.</span><span class="sxs-lookup"><span data-stu-id="b0823-130">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="b0823-131">Пользователи смогут вызвать Кортану, нажав кнопку "Микрофон Кортаны" в Teams.</span><span class="sxs-lookup"><span data-stu-id="b0823-131">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="b0823-132">Выключив слово (&#8220;привет, Кортана&#8221; или &#8220;Кортана&#8221;) будет отключена.</span><span class="sxs-lookup"><span data-stu-id="b0823-132">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="b0823-133">В этом примере показано обновление политики и включение голосовой помощи Кортаны с помощью push-кнопки и включения вызова слова.</span><span class="sxs-lookup"><span data-stu-id="b0823-133">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="b0823-134">На момент первоначального выпуска microsoft 365 корпоративный для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:</span><span class="sxs-lookup"><span data-stu-id="b0823-134">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="b0823-135">Мобильное приложение Teams не поддерживает активацию word, но в будущем оно будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="b0823-135">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="b0823-136">Комнаты Microsoft Teams в Windows и Устройствах с дисплеями Microsoft Teams поддерживают активацию word.</span><span class="sxs-lookup"><span data-stu-id="b0823-136">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="b0823-137">Пользовательский контроль</span><span class="sxs-lookup"><span data-stu-id="b0823-137">User control</span></span>

<span data-ttu-id="b0823-138">Отдельные пользователи могут попробовать голосовую помощь Кортаны на разных устройствах:</span><span class="sxs-lookup"><span data-stu-id="b0823-138">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="b0823-139">В мобильном приложении Teams выберите кнопку микрофона.</span><span class="sxs-lookup"><span data-stu-id="b0823-139">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="b0823-140">В комнатах Microsoft Teams выберите кнопку микрофона или скажите "Кортана".</span><span class="sxs-lookup"><span data-stu-id="b0823-140">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="b0823-141">Скажите "Кортана" на отображаемом устройстве Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0823-141">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="b0823-142">Вы можете управлять тем, включена ли Кортана в Teams для вашего устройства, используя параметр на устройстве.</span><span class="sxs-lookup"><span data-stu-id="b0823-142">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="b0823-143">Мобильное приложение Teams или отображение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0823-143">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="b0823-144">Откройте мобильное приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="b0823-144">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="b0823-145">Выберите **Параметры**  >  **Кортаны**.</span><span class="sxs-lookup"><span data-stu-id="b0823-145">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="b0823-146">Переместить **вкл.** или **Выкл.**</span><span class="sxs-lookup"><span data-stu-id="b0823-146">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="b0823-147">Отображение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0823-147">Microsoft Teams display</span></span>

  1. <span data-ttu-id="b0823-148">Перейдите на экран окружающего (домашнего) экрана Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0823-148">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="b0823-149">Выберите аватар пользователя, а затем — **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="b0823-149">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="b0823-150">Если Кортана включена, скажите "Кортана, перейдите в настройки".</span><span class="sxs-lookup"><span data-stu-id="b0823-150">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="b0823-151">Переместить **вкл.** или **Выкл.**</span><span class="sxs-lookup"><span data-stu-id="b0823-151">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="b0823-152">Комнаты Microsoft Teams в Windows</span><span class="sxs-lookup"><span data-stu-id="b0823-152">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="b0823-153">Внесение изменений на уровне устройства доступно, если Кортана включена на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="b0823-153">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="b0823-154">Кортана будет выключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0823-154">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="b0823-155">Чтобы включить Кортану на уровне устройства, эти атрибуты XML должны быть добавлены в XML-файл SkypeSettings:</span><span class="sxs-lookup"><span data-stu-id="b0823-155">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="b0823-156">Внесение изменений на уровне собрания доступно, если Кортана включена на уровне устройства.</span><span class="sxs-lookup"><span data-stu-id="b0823-156">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="b0823-157">Чтобы включить голосовую поддержку Кортаны во время собрания, переместите включит **или** **выкл.**.</span><span class="sxs-lookup"><span data-stu-id="b0823-157">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="b0823-158">После окончания собрания Кортана вернется к настройкам уровня устройства.</span><span class="sxs-lookup"><span data-stu-id="b0823-158">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
