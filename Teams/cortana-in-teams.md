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
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686445"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="67df0-103">Голосовая помощь Кортаны в Teams</span><span class="sxs-lookup"><span data-stu-id="67df0-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="67df0-104">Голосовая помощь Кортаны поддерживается в мобильных приложениях Microsoft Teams для iOS и Android, в комнатах Microsoft Teams для Windows и в Microsoft Teams отображается только для пользователей в США.</span><span class="sxs-lookup"><span data-stu-id="67df0-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="67df0-105">В настоящее время она недоступна для клиентов GCC, GCC-High, DoD и EDU.</span><span class="sxs-lookup"><span data-stu-id="67df0-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="67df0-106">Расширение до дополнительных языков и регионов будет происходить в будущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="67df0-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="67df0-107">Голосовая помощь Кортаны в комнатах Microsoft Teams выпущена в режиме предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="67df0-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="67df0-108">В предварительной версии Кортана поддерживается только в США с языком EN-US на устройствах, на которые подключены микрофоны В этом режиме.</span><span class="sxs-lookup"><span data-stu-id="67df0-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="67df0-109">Голосовая помощь Кортаны в мобильном приложении Teams, в комнатах Microsoft Teams для Windows и устройствах отображения Microsoft Teams позволяет пользователям Microsoft 365 корпоративный оптимизировать взаимодействие, совместную работу и задачи, связанные с собраниями, с использованием естественного языка речи.</span><span class="sxs-lookup"><span data-stu-id="67df0-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="67df0-110">Пользователи могут говорить с Кортаной, нажав кнопку микрофона в правом верхнем верхнем приложении Teams или нажав &#8220;Кортана&#8221; в комнате Microsoft Teams или при использовании дисплея Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67df0-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="67df0-111">Чтобы быстро общаться с командой без рук и в путь, пользователи могут делать запросы, например &#8220;позвонить&#8221; или &#8220;отправить сообщение на мое следующее собрание&#8221;.</span><span class="sxs-lookup"><span data-stu-id="67df0-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="67df0-112">Пользователи также могут присоединиться к собранию, &#8220;присоединиться к следующему собранию и&#8221; использовать голосовую помощь для обмена файлами, проверки календаря и многого другого.</span><span class="sxs-lookup"><span data-stu-id="67df0-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="67df0-113">Эти голосовые помощники оказания услуг, которые полностью соответствуют требованиям конфиденциальности, безопасности и соответствия требованиям Office 365, отражаются в Условиях использования [веб-служб](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) [(OST).](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="67df0-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="67df0-114">На изображении показана отправка чата с помощью Кортаны на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="67df0-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![Последовательность мобильных экранов с сеансом чата Кортаны](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="67df0-116">Администрирование и ограничения</span><span class="sxs-lookup"><span data-stu-id="67df0-116">Admin control and limitations</span></span>

<span data-ttu-id="67df0-117">Голосовая помощь Кортаны в Teams выполняется с помощью служб, которые полностью соответствуют требованиям конфиденциальности, безопасности и соответствия требованиям Office 365, как это отражается в Условиях использования веб-служб (OST).</span><span class="sxs-lookup"><span data-stu-id="67df0-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="67df0-118">Эта функция будет включена по умолчанию для клиентов.</span><span class="sxs-lookup"><span data-stu-id="67df0-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="67df0-119">Администраторы клиентов могут управлять тем, кто в клиенте может использовать голосовую помощь Кортаны в Teams с помощью политики (TeamsCortanaPolicy).</span><span class="sxs-lookup"><span data-stu-id="67df0-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="67df0-120">Эту политику можно настроить как на уровне учетной записи пользователя, так и на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="67df0-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="67df0-121">Администраторы могут использовать поле CortanaVoiceInvocationMode в этом средстве управления политикой, чтобы определить, отключена ли Кортана, включена ли она только при нажатии кнопки или при подавке wake word (применимо к устройствам, которые ее поддерживают, например, интерфейс Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="67df0-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="67df0-122">Администраторы могут использовать для управления этой политикой следующие командлеты PowerShell (в настоящее время политика недоступна в Центре администрирования Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="67df0-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="67df0-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="67df0-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="67df0-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="67df0-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="67df0-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="67df0-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="67df0-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="67df0-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="67df0-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="67df0-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="67df0-128">Например, с помощью приведенной ниже команды создается новая политика с именем &#8220;EmployeeCortanaPolicy&#8221; где отключена голосовая помощь Кортаны в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67df0-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="67df0-129">В этом примере показано обновление существующей политики с использованием имен &#8220;EmployeeCortanaPolicy&#8221; и включение голосовой помощи Кортаны в Microsoft Teams с помощью кнопки вызова.</span><span class="sxs-lookup"><span data-stu-id="67df0-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="67df0-130">Пользователи смогут вызвать Кортану, нажав кнопку микрофона Кортаны в Teams.</span><span class="sxs-lookup"><span data-stu-id="67df0-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="67df0-131">Пробуждает слово (&#8220;"Привет, Кортана&#8221;" или &#8220;Кортана&#8221;) будет отключена.</span><span class="sxs-lookup"><span data-stu-id="67df0-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="67df0-132">В этом примере показано обновление политики и включение голосовой помощи Кортаны с помощью кнопки и вызова word.</span><span class="sxs-lookup"><span data-stu-id="67df0-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="67df0-133">На момент первоначального выпуска для пользователей Microsoft 365 корпоративный в США на английском языке доступны следующие функции:</span><span class="sxs-lookup"><span data-stu-id="67df0-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="67df0-134">Мобильное приложение Teams не поддерживает активацию Word, но в будущем оно будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="67df0-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="67df0-135">Комнаты Microsoft Teams в Windows и Microsoft Teams поддерживают активацию Word.</span><span class="sxs-lookup"><span data-stu-id="67df0-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="67df0-136">Контроль пользователей</span><span class="sxs-lookup"><span data-stu-id="67df0-136">User control</span></span>

<span data-ttu-id="67df0-137">Отдельные пользователи могут попробовать голосовую помощь Кортаны на разных устройствах:</span><span class="sxs-lookup"><span data-stu-id="67df0-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="67df0-138">В мобильном приложении Teams выберите кнопку "Микрофон".</span><span class="sxs-lookup"><span data-stu-id="67df0-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="67df0-139">В комнатах Microsoft Teams выберите кнопку микрофона или скажите "Кортана".</span><span class="sxs-lookup"><span data-stu-id="67df0-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="67df0-140">Скажите "Кортана" в Microsoft Teams для отображения устройств.</span><span class="sxs-lookup"><span data-stu-id="67df0-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="67df0-141">Вы можете управлять тем, включена ли Кортана в Teams для вашего устройства, с помощью параметра устройства.</span><span class="sxs-lookup"><span data-stu-id="67df0-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="67df0-142">Мобильное приложение Teams или отображение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67df0-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="67df0-143">Откройте мобильное приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="67df0-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="67df0-144">Выберите **"Параметры**  >  **Кортаны".**</span><span class="sxs-lookup"><span data-stu-id="67df0-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="67df0-145">Включите или **выключите** **его.**</span><span class="sxs-lookup"><span data-stu-id="67df0-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="67df0-146">Отображение Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67df0-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="67df0-147">Перейдите на экран окружающего (домашнего) экрана Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67df0-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="67df0-148">Выберите аватар пользователя, а затем — **"Параметры".**</span><span class="sxs-lookup"><span data-stu-id="67df0-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="67df0-149">Если Кортана включена, скажите "Кортана, перейдите в "Параметры".</span><span class="sxs-lookup"><span data-stu-id="67df0-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="67df0-150">Включите или **выключите** **его.**</span><span class="sxs-lookup"><span data-stu-id="67df0-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="67df0-151">Комнаты Microsoft Teams в Windows</span><span class="sxs-lookup"><span data-stu-id="67df0-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="67df0-152">Внесение изменений на уровне устройства доступно, если Кортана включена на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="67df0-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="67df0-153">Кортана будет выключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67df0-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="67df0-154">Чтобы включить Кортану на уровне устройства, в XML-файл SkypeSettings необходимо добавить указанные ниже XML-атрибуты.</span><span class="sxs-lookup"><span data-stu-id="67df0-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="67df0-155">Внесение изменений на уровне собрания доступно, если Кортана включена на уровне устройства.</span><span class="sxs-lookup"><span data-stu-id="67df0-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="67df0-156">Чтобы включить голосовую поддержку Кортаны во время  собрания, переместите или выключите **ее.**</span><span class="sxs-lookup"><span data-stu-id="67df0-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="67df0-157">После окончания собрания Кортана возвращается к установленным настройкам уровня устройства.</span><span class="sxs-lookup"><span data-stu-id="67df0-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
