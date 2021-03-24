---
title: Настройка клиентского опыта в Skype для бизнеса 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как настроить клиентскую возможность для пользователей Skype для бизнеса.
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096013"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="4099b-103">Настройка клиентского опыта в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="4099b-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="4099b-104">**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить клиентскую возможность для пользователей Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="4099b-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="4099b-105">Skype for Business 2015 предоставляет новый пользовательский интерфейс, основанный на пользовательском продукте Skype.</span><span class="sxs-lookup"><span data-stu-id="4099b-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="4099b-106">Помимо всех функций Lync, Skype для бизнеса предоставляет новые функции с упрощенным управлением и знакомыми значками.</span><span class="sxs-lookup"><span data-stu-id="4099b-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="4099b-107">Подробные сведения о новом клиенте см. в обзоре [Обзор Skype для бизнеса.](https://go.microsoft.com/fwlink/?LinkId=529022)</span><span class="sxs-lookup"><span data-stu-id="4099b-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="4099b-108">Skype для бизнеса Server поддерживает новый клиентский опыт Skype для бизнеса, а также клиентскую службу Lync.</span><span class="sxs-lookup"><span data-stu-id="4099b-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="4099b-109">В качестве администратора вы можете выбрать предпочтительный клиентский опыт для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4099b-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="4099b-110">Например, может потребоваться развернуть клиентский опыт Lync до тех пор, пока пользователи в организации не будут полностью обучены новому опыту Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4099b-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="4099b-111">Или, если вы еще не обновили всех пользователей до Skype для бизнеса Server, вы можете захотеть, чтобы у всех пользователей был одинаковый клиентский опыт до тех пор, пока все не будут обновлены до нового сервера.</span><span class="sxs-lookup"><span data-stu-id="4099b-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4099b-112">Если в вашей организации развернуты Skype для бизнеса Server и Lync Server, клиентская программа по умолчанию будет отличаться в зависимости от версий сервера и параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4099b-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="4099b-113">Когда пользователи впервые запускают Skype для бизнеса, они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали клиентскую возможность Lync.</span><span class="sxs-lookup"><span data-stu-id="4099b-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="4099b-114">Через несколько минут пользователям будет предложено перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="4099b-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="4099b-115">Дополнительные сведения см. в **разделе First launch client behaviour** later in this topic.</span><span class="sxs-lookup"><span data-stu-id="4099b-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4099b-116">Клиентская возможность Lync 2013 не является вариантом для клиентских версий Skype для бизнеса 2016 или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="4099b-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="4099b-117">Прежде чем пытаться настроить клиентскую среду для использования клиента Lync 2013, проверьте клиентскую версию, чтобы убедиться, что она не начинается с номера 16; например: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="4099b-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="4099b-118">Настройка взаимодействия с клиентом</span><span class="sxs-lookup"><span data-stu-id="4099b-118">Configure the client experience</span></span>

<span data-ttu-id="4099b-119">Вы можете указать клиентский опыт, который увидят пользователи в организации с помощью комлета **Set-CSClientPolicy** с параметром EnableSkypeUI:</span><span class="sxs-lookup"><span data-stu-id="4099b-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="4099b-120">где XdsIdentity ссылается на глобальную политику или именоваемую политику сайта.</span><span class="sxs-lookup"><span data-stu-id="4099b-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="4099b-121">Следующая команда выбирает клиентский интерфейс Skype для бизнеса для всех пользователей в организации, затронутых глобальной политикой (помните, политики сайта или пользователя переопределяют глобальную политику):</span><span class="sxs-lookup"><span data-stu-id="4099b-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="4099b-122">Следующая команда выбирает клиентскую возможность Lync для всех пользователей в организации, затронутых глобальной политикой:</span><span class="sxs-lookup"><span data-stu-id="4099b-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="4099b-123">Следующая команда выбирает клиентский опыт Skype для бизнеса для всех пользователей сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="4099b-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="4099b-124">Если вы хотите настроить клиентский интерфейс для определенных пользователей в организации, можно создать новую политику пользователей с помощью комлета **New-CsClientPolicy,** а затем назначить политику конкретным пользователям с помощью cmdlet **Grant-CsClientPolicy.**</span><span class="sxs-lookup"><span data-stu-id="4099b-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="4099b-125">Например, следующая команда создает новую клиентскую политику SalesClientUI, которая выбирает клиентский интерфейс Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="4099b-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="4099b-126">Следующая команда назначает политику SalesClientUI всем сотрудникам отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="4099b-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="4099b-127">Поведение клиентов первого запуска</span><span class="sxs-lookup"><span data-stu-id="4099b-127">First launch client behaviors</span></span>

<span data-ttu-id="4099b-128">По умолчанию при первом запуске Skype для бизнеса 2015 пользователи всегда будут видеть пользовательский интерфейс Skype для бизнеса , даже если вы выбрали клиентскую возможность Lync, установив значение параметра EnableSkypeUI $False как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="4099b-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="4099b-129">Через несколько минут пользователям будет предложено перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="4099b-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="4099b-130">Если вы хотите отобразить пользовательский интерфейс Lync при первом запуске клиентом Skype для бизнеса, выполните следующие действия перед первым запуском клиента после обновления:</span><span class="sxs-lookup"><span data-stu-id="4099b-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="4099b-131">Подтвердим, что значение $False в используемой политике,  `EnableSkypeUI` как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="4099b-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="4099b-132">Обновление системного реестра на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="4099b-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="4099b-133">Это необходимо сделать перед первым запуском клиентом Skype для бизнеса, и это необходимо сделать только один раз.</span><span class="sxs-lookup"><span data-stu-id="4099b-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="4099b-134">Сведения о том, как создать объект групповой политики для обновления реестра на компьютере, присоединимом к домену, см. в разделе далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4099b-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="4099b-135">В **ключе [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** создайте новое **двоичное** значение.</span><span class="sxs-lookup"><span data-stu-id="4099b-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="4099b-136">Имя **Value должно** быть **EnableSkypeUI,** а данные **значения** должны быть за установлены до **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="4099b-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="4099b-137">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4099b-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="4099b-138">Пользовательский интерфейс Lync будет отображаться при первом запуске клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4099b-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="4099b-139">Управление отображением учебника по экрану Welcome</span><span class="sxs-lookup"><span data-stu-id="4099b-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="4099b-140">Когда пользователи открывают клиент Skype для бизнеса, по умолчанию отображается экран Welcome, который включает  *7* быстрых советов, которые большинство людей просят .</span><span class="sxs-lookup"><span data-stu-id="4099b-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="4099b-141">Вы можете отключить отображение экрана Welcome, но все же разрешить пользователям доступ к учебнику, добавив следующее значение реестра на клиентский компьютер:</span><span class="sxs-lookup"><span data-stu-id="4099b-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="4099b-142">В **ключе [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новое **значение DWORD (32-bit).**</span><span class="sxs-lookup"><span data-stu-id="4099b-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="4099b-143">Имя **Значения должно** быть **IsBasicTutorialSeenByUser,** а данные значения должны быть за установлены **до 1**. </span><span class="sxs-lookup"><span data-stu-id="4099b-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="4099b-144">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4099b-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="4099b-145">Отключение клиентского учебника</span><span class="sxs-lookup"><span data-stu-id="4099b-145">Turn off the client tutorial</span></span>

<span data-ttu-id="4099b-146">Если вы не хотите, чтобы пользователи могли получить доступ к учебнику, вы можете отключить клиентский учебник со следующим значением реестра:</span><span class="sxs-lookup"><span data-stu-id="4099b-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="4099b-147">В **ключе [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новое **значение DWORD (32-bit).**</span><span class="sxs-lookup"><span data-stu-id="4099b-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="4099b-148">Имя **Value должно** быть **TutorialFeatureEnabled,** а данные **значения** должны быть заданы **0**.</span><span class="sxs-lookup"><span data-stu-id="4099b-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="4099b-149">Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="4099b-150">Вы можете включить учебник, установив значение **данных** до **1**.</span><span class="sxs-lookup"><span data-stu-id="4099b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="4099b-151">Поведение клиентов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4099b-151">Default client behaviors</span></span>

<span data-ttu-id="4099b-152">Если в вашей организации развернуты Skype для бизнеса Server и Lync Server, клиентский опыт будет отличаться в зависимости от версий сервера и параметра пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="4099b-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="4099b-153">В следующей таблице показан начальный клиентский интерфейс, основанный на версии сервера и параметре пользовательского интерфейса:</span><span class="sxs-lookup"><span data-stu-id="4099b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="4099b-154">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="4099b-154">**Server version**</span></span>|<span data-ttu-id="4099b-155">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4099b-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4099b-156">**Клиентский опыт**</span><span class="sxs-lookup"><span data-stu-id="4099b-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4099b-157">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4099b-157">Skype for Business Server</span></span> |<span data-ttu-id="4099b-158">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4099b-158">Default</span></span>  <br/> |<span data-ttu-id="4099b-159">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4099b-160">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4099b-160">Skype for Business Server</span></span>  |<span data-ttu-id="4099b-161">Верно</span><span class="sxs-lookup"><span data-stu-id="4099b-161">True</span></span>  <br/> |<span data-ttu-id="4099b-162">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4099b-163">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4099b-163">Skype for Business Server</span></span>  |<span data-ttu-id="4099b-164">False</span><span class="sxs-lookup"><span data-stu-id="4099b-164">False</span></span>  <br/> |<span data-ttu-id="4099b-165">Пользователю было предложено перейти в режим Lync (пользователь может перейти на Skype для бизнеса позже, если изменить параметр пользовательского интерфейса на $true)</span><span class="sxs-lookup"><span data-stu-id="4099b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4099b-166">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="4099b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4099b-167">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4099b-167">Default</span></span>  <br/> |<span data-ttu-id="4099b-168">Пользователю было предложено перейти в режим Lync (пользователь может перейти на Skype для бизнеса позже, если изменить параметр пользовательского интерфейса на $true)</span><span class="sxs-lookup"><span data-stu-id="4099b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4099b-169">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="4099b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4099b-170">Верно</span><span class="sxs-lookup"><span data-stu-id="4099b-170">True</span></span>  <br/> |<span data-ttu-id="4099b-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4099b-172">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="4099b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4099b-173">False</span><span class="sxs-lookup"><span data-stu-id="4099b-173">False</span></span>  <br/> |<span data-ttu-id="4099b-174">Пользователю было предложено перейти в режим Lync (пользователь может перейти на Skype для бизнеса позже, если изменить параметр пользовательского интерфейса на $true)</span><span class="sxs-lookup"><span data-stu-id="4099b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4099b-175">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="4099b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4099b-176">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4099b-176">Default</span></span>  <br/> |<span data-ttu-id="4099b-177">Пользователь попросил перейти в режим Lync (пользователь не может перейти на Skype для бизнеса позже)</span><span class="sxs-lookup"><span data-stu-id="4099b-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="4099b-178">В следующей таблице показана клиентская запись, когда администратор изменяет начальный параметр интерфейса Skype:</span><span class="sxs-lookup"><span data-stu-id="4099b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="4099b-179">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="4099b-179">**Server version**</span></span>|<span data-ttu-id="4099b-180">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4099b-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4099b-181">**Пользовательский интерфейс клиента = Lync**</span><span class="sxs-lookup"><span data-stu-id="4099b-181">**Client UI = Lync**</span></span>|<span data-ttu-id="4099b-182">**Пользовательский интерфейс клиента = Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="4099b-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4099b-183">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4099b-183">Skype for Business Server</span></span> |<span data-ttu-id="4099b-184">Верно</span><span class="sxs-lookup"><span data-stu-id="4099b-184">True</span></span>  <br/> |<span data-ttu-id="4099b-185">Пользователь попросил перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4099b-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4099b-187">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4099b-187">Skype for Business Server</span></span> |<span data-ttu-id="4099b-188">False</span><span class="sxs-lookup"><span data-stu-id="4099b-188">False</span></span>  <br/> |<span data-ttu-id="4099b-189">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-189">Lync mode</span></span>  <br/> |<span data-ttu-id="4099b-190">Пользователю было предложено перейти на режим Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4099b-191">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="4099b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4099b-192">Верно</span><span class="sxs-lookup"><span data-stu-id="4099b-192">True</span></span>  <br/> |<span data-ttu-id="4099b-193">Пользователь попросил перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4099b-194">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4099b-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4099b-195">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="4099b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4099b-196">False</span><span class="sxs-lookup"><span data-stu-id="4099b-196">False</span></span>  <br/> |<span data-ttu-id="4099b-197">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-197">Lync mode</span></span>  <br/> |<span data-ttu-id="4099b-198">Пользователю было предложено перейти на режим Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4099b-199">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="4099b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4099b-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="4099b-200">Default</span></span>  <br/> |<span data-ttu-id="4099b-201">Режим Lync (не может перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="4099b-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="4099b-202">Режим Lync (не может перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="4099b-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="4099b-203">Версии исправлений, необходимые для управления конфигурацией клиента Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="4099b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="4099b-204">Накопительное обновление Lync Server 2010 — февраль 2015 г. (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4099b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="4099b-205">Сведения см. [в обновлениях для Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="4099b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="4099b-206">Накопительное обновление Lync Server 2013 — декабрь 2014 г. (5.0.8308.857) для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4099b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="4099b-207">Сведения см. [в обновлениях для Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="4099b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="4099b-208">Создание объекта групповой политики для изменения реестра на компьютере, присоединимом к домену.</span><span class="sxs-lookup"><span data-stu-id="4099b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="4099b-209">Обновление реестра для отображения клиентского интерфейса Lync при первом запуске клиентом Skype для бизнеса 2015 должно быть сделано только один раз.</span><span class="sxs-lookup"><span data-stu-id="4099b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="4099b-210">Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект, чтобы создать новое значение, а не обновить данные value.</span><span class="sxs-lookup"><span data-stu-id="4099b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="4099b-211">При применении GPO, если нового значения не существует, GPO создаст его и закадрит данные Значения до 0.</span><span class="sxs-lookup"><span data-stu-id="4099b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="4099b-212">В следующей процедуре описывается изменение реестра таким образом, чтобы клиент Lync отображался при первом запуске клиентом Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="4099b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="4099b-213">Вы также можете использовать эту процедуру для обновления реестра, чтобы отключить учебник по экрану Welcome, как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="4099b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="4099b-214">Создание GPO</span><span class="sxs-lookup"><span data-stu-id="4099b-214">To create the GPO</span></span>

1. <span data-ttu-id="4099b-215">Запустите **консоль управления групповой политикой.**</span><span class="sxs-lookup"><span data-stu-id="4099b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="4099b-216">Сведения об использовании консоли управления групповой политикой см. в консоли [управления групповой политикой.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="4099b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="4099b-217">Щелкните правой кнопкой мыши узел **объекты групповой политики** и **выберите New** в меню.</span><span class="sxs-lookup"><span data-stu-id="4099b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="4099b-218">В **диалоговом окну New GPO** введите имя GPO, например MakeLyncDefaultUI, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="4099b-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4099b-219">Щелкните правой кнопкой мыши по только что созданному новому GPO, а затем выберите **Изменить** из меню.</span><span class="sxs-lookup"><span data-stu-id="4099b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="4099b-220">В **редакторе управления групповой политикой** расширяй конфигурацию **пользователей,** расширяй **настройки,** расширяй параметры **Windows,** а затем выберите **узел реестра.**</span><span class="sxs-lookup"><span data-stu-id="4099b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="4099b-221">Щелкните правой кнопкой мыши узел **реестра,** а затем выберите **элемент New**  >  **Registry Item**.</span><span class="sxs-lookup"><span data-stu-id="4099b-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="4099b-222">В **диалоговом октаге New Registry Properties** обновите следующее:</span><span class="sxs-lookup"><span data-stu-id="4099b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="4099b-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="4099b-223">**Field**</span></span>|<span data-ttu-id="4099b-224">**Значение для выбора или ввода**</span><span class="sxs-lookup"><span data-stu-id="4099b-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4099b-225">**Действие**</span><span class="sxs-lookup"><span data-stu-id="4099b-225">**Action**</span></span> <br/> |<span data-ttu-id="4099b-226">**Создание**</span><span class="sxs-lookup"><span data-stu-id="4099b-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="4099b-227">**Куст**</span><span class="sxs-lookup"><span data-stu-id="4099b-227">**Hive**</span></span> <br/> | <span data-ttu-id="4099b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="4099b-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="4099b-229">**Путь ключа**</span><span class="sxs-lookup"><span data-stu-id="4099b-229">**Key Path**</span></span> <br/> |<span data-ttu-id="4099b-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="4099b-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="4099b-231">**Имя значения**</span><span class="sxs-lookup"><span data-stu-id="4099b-231">**Value name**</span></span> <br/> |<span data-ttu-id="4099b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="4099b-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="4099b-233">**Тип значения**</span><span class="sxs-lookup"><span data-stu-id="4099b-233">**Value type**</span></span> <br/> |<span data-ttu-id="4099b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="4099b-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="4099b-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="4099b-235">**Value data**</span></span> <br/> |<span data-ttu-id="4099b-236">00000000</span><span class="sxs-lookup"><span data-stu-id="4099b-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="4099b-237">Нажмите **кнопку ОК,** чтобы сохранить изменения, а затем закрыть GPO.</span><span class="sxs-lookup"><span data-stu-id="4099b-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="4099b-238">Далее необходимо связать созданный GPO с группой пользователей, на которую нужно назначить политику, например с OU.</span><span class="sxs-lookup"><span data-stu-id="4099b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="4099b-239">Использование GPO для назначения политики</span><span class="sxs-lookup"><span data-stu-id="4099b-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="4099b-240">В консоли управления групповой политикой щелкните правой кнопкой мыши по OU, на который необходимо назначить политику, а затем выберите ссылку на **существующую GPO.**</span><span class="sxs-lookup"><span data-stu-id="4099b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="4099b-241">В **диалоговом окте Выберите GPO** выберите созданную GPO и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="4099b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="4099b-242">На компьютере целевого пользователя откройте командную подсказку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4099b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="4099b-243">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4099b-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="4099b-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="4099b-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="4099b-245">Вы должны увидеть "Присвоенные объекты групповой политики" с именем созданного вами GPO, отображаемого ниже.</span><span class="sxs-lookup"><span data-stu-id="4099b-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="4099b-246">Вы также можете убедиться, что GPO успешно обновила реестр на компьютере пользователя, изучив реестр.</span><span class="sxs-lookup"><span data-stu-id="4099b-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="4099b-247">Откройте редактор реестра и перейдите к **клавише [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].**</span><span class="sxs-lookup"><span data-stu-id="4099b-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="4099b-248">Если GPO успешно обновила реестр, вы увидите значение EnableSkypeUI со значением 0.</span><span class="sxs-lookup"><span data-stu-id="4099b-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
