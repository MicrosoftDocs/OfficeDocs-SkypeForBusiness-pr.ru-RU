---
title: Настройка интерфейса клиента в Skype для бизнеса 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы научиться настраивать взаимодействие с клиентами для пользователей Skype для бизнеса.'
ms.openlocfilehash: ea1d38693291ebfa7d7cc4f8893b0aa6ec1c0d83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234456"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="e56c4-103">Настройка интерфейса клиента в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="e56c4-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="e56c4-104">**Сводка:** В этой статье рассказывается о том, как настроить интерфейс клиента для пользователей Skype для бизнеса 2015.</span><span class="sxs-lookup"><span data-stu-id="e56c4-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="e56c4-105">Skype для бизнеса 2015 обеспечивает новый пользовательский интерфейс, основанный на потребительских интерфейсах Skype.</span><span class="sxs-lookup"><span data-stu-id="e56c4-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="e56c4-106">Помимо всех функций Lync, в Skype для бизнеса предусмотрены новые функции, упрощенные элементы управления и знакомые значки.</span><span class="sxs-lookup"><span data-stu-id="e56c4-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="e56c4-107">Подробные сведения о новом интерфейсе клиента можно найти в статьях знакомство со [Skype для бизнеса](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="e56c4-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="e56c4-108">Skype для бизнеса Server поддерживает новый клиентский интерфейс Skype для бизнеса, а также взаимодействие с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="e56c4-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="e56c4-109">Администратор может выбрать для пользователей предпочтительный режим взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e56c4-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="e56c4-110">Например, вам может потребоваться развернуть взаимодействие с клиентом Lync, пока пользователи в вашей организации не будут полностью прошли обучение в новом интерфейсе Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e56c4-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="e56c4-111">Если вы еще не обновили все пользователи в Skype для бизнеса Server, вам может потребоваться, чтобы все пользователи могли использовать одинаковые возможности клиента, пока не будут обновлены до нового сервера.</span><span class="sxs-lookup"><span data-stu-id="e56c4-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e56c4-112">Если в вашей организации одновременно развернуты и Skype для бизнеса, и сервер Lync Server, интерфейс по умолчанию будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e56c4-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="e56c4-113">Когда пользователи запускают Skype для бизнеса в первый раз, они всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали взаимодействие с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="e56c4-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="e56c4-114">Через несколько минут пользователи просят перейти в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="e56c4-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="e56c4-115">Дополнительные сведения см. в разделе **Режим работы клиента при первом запуске** далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e56c4-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e56c4-116">Взаимодействие с клиентом Lync 2013 не поддерживается в версиях клиента Skype для бизнеса 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e56c4-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="e56c4-117">Перед настройкой клиентской среды на использование клиента Lync 2013 убедитесь, что версия клиента не начинается с цифр "16" (например: 16.x.x.x).</span><span class="sxs-lookup"><span data-stu-id="e56c4-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="e56c4-118">Настройка взаимодействия с клиентом</span><span class="sxs-lookup"><span data-stu-id="e56c4-118">Configure the client experience</span></span>

<span data-ttu-id="e56c4-119">Командлет **Set-CSClientPolicy** с параметром EnableSkypeUI позволяет настроить взаимодействие с клиентом для пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="e56c4-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="e56c4-120">Здесь XdsIdentity означает глобальную политику или именованную политику сайта.</span><span class="sxs-lookup"><span data-stu-id="e56c4-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="e56c4-121">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей в Организации, которым затронула Глобальная политика (Помните, что политики сайтов или пользователей переопределяют глобальную политику).</span><span class="sxs-lookup"><span data-stu-id="e56c4-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="e56c4-122">Следующая команда выбирает взаимодействие с клиентом Lync для всех пользователей в вашей организации, затрагиваемых глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="e56c4-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="e56c4-123">Следующая команда выбирает взаимодействие с клиентом Skype для бизнеса для всех пользователей на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="e56c4-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="e56c4-124">Если вы хотите настроить взаимодействие с клиентами для конкретных пользователей в Организации, вы можете создать новую политику пользователей с помощью командлета **New-CsClientPolicy** , а затем назначить политику для определенных пользователей с помощью функции **Grant-CsClientPolicy** Командлет.</span><span class="sxs-lookup"><span data-stu-id="e56c4-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e56c4-125">Например, следующая команда создает новую политику клиента, Салесклиентуи, которая выбирает взаимодействие с клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e56c4-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="e56c4-126">При выполнении следующей команды политика SalesClientUI назначается всем участникам из отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="e56c4-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="e56c4-127">Режим работы клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="e56c4-127">First launch client behaviors</span></span>

<span data-ttu-id="e56c4-128">По умолчанию при первом запуске Skype для бизнеса 2015 пользователи всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали взаимодействие с клиентом Lync, задав для параметра Енаблескипеуи значение, равное $False, как описано ниже. заранее.</span><span class="sxs-lookup"><span data-stu-id="e56c4-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="e56c4-129">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="e56c4-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="e56c4-130">Чтобы отобразить интерфейс Lync при первом запуске клиента Skype для бизнеса, выполните следующие действия до того, как клиент будет запущен в первый раз после обновления.</span><span class="sxs-lookup"><span data-stu-id="e56c4-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="e56c4-131">Убедитесь в том, что `EnableSkypeUI` значение параметра установлено на $false в той политике, которую вы используете, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="e56c4-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="e56c4-p106">Обновите системный реестр на компьютере пользователя. Это необходимо сделать до первого запуска клиента Skype для бизнеса. Действие выполняется всего один раз. Сведения о создании объекта групповой политики для обновления реестра на присоединенном к домену компьютере см. далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e56c4-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="e56c4-135">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** создайте новое **двоичное** значение.</span><span class="sxs-lookup"><span data-stu-id="e56c4-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="e56c4-136">**Имя значения** должно быть **EnableSkypeUI**. Для **данных значения** задайте **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="e56c4-137">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e56c4-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="e56c4-138">Теперь интерфейс Lync будет отображаться при первом запуске клиента Skype для бизнеса пользователями.</span><span class="sxs-lookup"><span data-stu-id="e56c4-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="e56c4-139">Руководство по управлению отображением экрана приветствия</span><span class="sxs-lookup"><span data-stu-id="e56c4-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="e56c4-140">Когда пользователи открывают клиент Skype для бизнеса, по умолчанию отображается экран приветствия, включающий *семь советов*, которые нужно запросить.</span><span class="sxs-lookup"><span data-stu-id="e56c4-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="e56c4-141">Вы можете отключить отображение экрана приветствия, но по-прежнему предоставить пользователям доступ к учебнику, добавив следующий параметр реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="e56c4-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="e56c4-p108">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новый **Параметр DWORD (32-разрядный)**. Для параметра **Имя значение** необходимо указать значение **IsBasicTutorialSeenByUser**, для параметра **Данные значения** — **1**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="e56c4-144">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e56c4-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="e56c4-145">Отключение руководства в клиенте</span><span class="sxs-lookup"><span data-stu-id="e56c4-145">Turn off the client tutorial</span></span>

<span data-ttu-id="e56c4-146">Чтобы ваши пользователи не могли получить доступ к руководству, отключите руководство клиента с помощью следующего значения реестра:</span><span class="sxs-lookup"><span data-stu-id="e56c4-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="e56c4-p109">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новый **Параметр DWORD (32-разрядный)**. Для параметра **Имя значение** необходимо указать значение **TutorialFeatureEnabled**, для параметра **Данные значения** — **0**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="e56c4-149">Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="e56c4-150">Вы можете вернуть доступ к руководству, присвоив параметру **Данные значения** значение **1**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="e56c4-151">Режимы работы клиента по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56c4-151">Default client behaviors</span></span>

<span data-ttu-id="e56c4-152">Если в вашей организации одновременно развернуты и Skype для бизнеса, и сервер Lync Server, взаимодействие с клиентом будет отличаться в зависимости от версии сервера и параметров пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="e56c4-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="e56c4-153">В следующей таблице указан первоначальный режим взаимодействия с клиентом в зависимости от версии сервера и параметра пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e56c4-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="e56c4-154">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="e56c4-154">**Server version**</span></span>|<span data-ttu-id="e56c4-155">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="e56c4-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e56c4-156">**Взаимодействие с клиентом**</span><span class="sxs-lookup"><span data-stu-id="e56c4-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e56c4-157">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e56c4-157">Skype for Business Server</span></span> |<span data-ttu-id="e56c4-158">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56c4-158">Default</span></span>  <br/> |<span data-ttu-id="e56c4-159">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e56c4-160">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e56c4-160">Skype for Business Server</span></span>  |<span data-ttu-id="e56c4-161">True</span><span class="sxs-lookup"><span data-stu-id="e56c4-161">True</span></span>  <br/> |<span data-ttu-id="e56c4-162">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e56c4-163">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e56c4-163">Skype for Business Server</span></span>  |<span data-ttu-id="e56c4-164">False</span><span class="sxs-lookup"><span data-stu-id="e56c4-164">False</span></span>  <br/> |<span data-ttu-id="e56c4-165">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="e56c4-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e56c4-166">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="e56c4-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e56c4-167">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56c4-167">Default</span></span>  <br/> |<span data-ttu-id="e56c4-168">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="e56c4-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e56c4-169">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="e56c4-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e56c4-170">True</span><span class="sxs-lookup"><span data-stu-id="e56c4-170">True</span></span>  <br/> |<span data-ttu-id="e56c4-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e56c4-172">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="e56c4-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e56c4-173">False</span><span class="sxs-lookup"><span data-stu-id="e56c4-173">False</span></span>  <br/> |<span data-ttu-id="e56c4-174">Пользователь запросят перейти в режим Lync (пользователь может переключиться на Skype для бизнеса позже, если вы измените параметр UI на $true).</span><span class="sxs-lookup"><span data-stu-id="e56c4-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e56c4-175">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="e56c4-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e56c4-176">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56c4-176">Default</span></span>  <br/> |<span data-ttu-id="e56c4-177">Пользователь запросят перейти в режим Lync (пользователь не может переключиться на Skype для бизнеса позже)</span><span class="sxs-lookup"><span data-stu-id="e56c4-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="e56c4-178">В следующей таблице показано, как администратор изменяет первоначальные параметры пользовательского интерфейса Skype.</span><span class="sxs-lookup"><span data-stu-id="e56c4-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="e56c4-179">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="e56c4-179">**Server version**</span></span>|<span data-ttu-id="e56c4-180">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="e56c4-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e56c4-181">**Пользовательский интерфейс клиента = Lync**</span><span class="sxs-lookup"><span data-stu-id="e56c4-181">**Client UI = Lync**</span></span>|<span data-ttu-id="e56c4-182">**Клиентский пользовательский интерфейс = Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="e56c4-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e56c4-183">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e56c4-183">Skype for Business Server</span></span> |<span data-ttu-id="e56c4-184">True</span><span class="sxs-lookup"><span data-stu-id="e56c4-184">True</span></span>  <br/> |<span data-ttu-id="e56c4-185">Пользователь попросят перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e56c4-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e56c4-187">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e56c4-187">Skype for Business Server</span></span> |<span data-ttu-id="e56c4-188">False</span><span class="sxs-lookup"><span data-stu-id="e56c4-188">False</span></span>  <br/> |<span data-ttu-id="e56c4-189">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-189">Lync mode</span></span>  <br/> |<span data-ttu-id="e56c4-190">Пользователь запросят перейти в режим Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e56c4-191">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="e56c4-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e56c4-192">True</span><span class="sxs-lookup"><span data-stu-id="e56c4-192">True</span></span>  <br/> |<span data-ttu-id="e56c4-193">Пользователь попросят перейти на Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e56c4-194">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e56c4-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e56c4-195">Lync Server 2010 или Lync Server 2013 (с правильными исправлениями)</span><span class="sxs-lookup"><span data-stu-id="e56c4-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e56c4-196">False</span><span class="sxs-lookup"><span data-stu-id="e56c4-196">False</span></span>  <br/> |<span data-ttu-id="e56c4-197">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-197">Lync mode</span></span>  <br/> |<span data-ttu-id="e56c4-198">Пользователь запросят перейти в режим Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e56c4-199">Lync Server 2010 или Lync Server 2013 (без исправлений)</span><span class="sxs-lookup"><span data-stu-id="e56c4-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e56c4-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56c4-200">Default</span></span>  <br/> |<span data-ttu-id="e56c4-201">Режим Lync (не удается перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="e56c4-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="e56c4-202">Режим Lync (не удается перейти на Skype для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="e56c4-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="e56c4-203">Для управления конфигурацией клиента Skype для бизнеса требуются следующие версии исправлений:</span><span class="sxs-lookup"><span data-stu-id="e56c4-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="e56c4-204">Lync Server 2010 — февраля 2015 (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e56c4-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="e56c4-205">Дополнительные сведения можно найти в разделе [Обновление для Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="e56c4-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="e56c4-206">Lync Server 2013 – Декабрь 2014 (5.0.8308.857) для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e56c4-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="e56c4-207">Дополнительные сведения можно найти в разделе [Обновление для Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="e56c4-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="e56c4-208">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="e56c4-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="e56c4-209">Обновление реестра для отображения взаимодействия с клиентом Lync при первом запуске клиента Skype для бизнеса 2015 следует выполнять только один раз.</span><span class="sxs-lookup"><span data-stu-id="e56c4-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="e56c4-210">Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения, а не обновлять данные значения.</span><span class="sxs-lookup"><span data-stu-id="e56c4-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="e56c4-211">Если при применении GPO новое значение не существует, оно будет создано, а для данных значения будет задано значение 0.</span><span class="sxs-lookup"><span data-stu-id="e56c4-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="e56c4-212">Ниже описано, как изменить реестр таким образом, чтобы при первом запуске клиента Skype для бизнеса 2015 на экране отображался интерфейс пользователя Lync.</span><span class="sxs-lookup"><span data-stu-id="e56c4-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="e56c4-213">Эту процедуру можно также использовать для того, чтобы отключить руководство на экране приветствия, как было описано ранее.</span><span class="sxs-lookup"><span data-stu-id="e56c4-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="e56c4-214">Создание GPO</span><span class="sxs-lookup"><span data-stu-id="e56c4-214">To create the GPO</span></span>

1. <span data-ttu-id="e56c4-215">Запустите **Консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="e56c4-216">Сведения о работе с консолью управления групповыми политиками см. в разделе [Консоль управления групповыми политиками](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="e56c4-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="e56c4-217">Щелкните правой кнопкой мыши узел **Объекты групповой политики** и выберите в меню пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="e56c4-218">В диалоговом окне **Новый объект групповой политики** введите название объекта, напримерMakeLyncDefaultUI, затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="e56c4-219">Щелкните правой кнопкой мыши только что созданный объект групповой политики и выберите в меню пункт **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="e56c4-220">В **Редакторе управления групповыми политиками** разверните папки **Конфигурация пользователя**, **Параметры**, **Параметры Windows** и выберите узел **Реестр**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="e56c4-221">Щелкните правой кнопкой мыши на узле **Реестр** и выберите **Создать** > **Элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="e56c4-222">В диалоговом окне **Новые свойства реестра** обновите следующие поля.</span><span class="sxs-lookup"><span data-stu-id="e56c4-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="e56c4-223">**Поле**</span><span class="sxs-lookup"><span data-stu-id="e56c4-223">**Field**</span></span>|<span data-ttu-id="e56c4-224">**Значение для выбора или ввода**</span><span class="sxs-lookup"><span data-stu-id="e56c4-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e56c4-225">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e56c4-225">**Action**</span></span> <br/> |<span data-ttu-id="e56c4-226">**Создание**</span><span class="sxs-lookup"><span data-stu-id="e56c4-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="e56c4-227">**Куст**</span><span class="sxs-lookup"><span data-stu-id="e56c4-227">**Hive**</span></span> <br/> | <span data-ttu-id="e56c4-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="e56c4-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="e56c4-229">**Ключевой путь**</span><span class="sxs-lookup"><span data-stu-id="e56c4-229">**Key Path**</span></span> <br/> |<span data-ttu-id="e56c4-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="e56c4-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="e56c4-231">**Имя значения**</span><span class="sxs-lookup"><span data-stu-id="e56c4-231">**Value name**</span></span> <br/> |<span data-ttu-id="e56c4-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="e56c4-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="e56c4-233">**Тип значения**</span><span class="sxs-lookup"><span data-stu-id="e56c4-233">**Value type**</span></span> <br/> |<span data-ttu-id="e56c4-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e56c4-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="e56c4-235">**Данные значения**</span><span class="sxs-lookup"><span data-stu-id="e56c4-235">**Value data**</span></span> <br/> |<span data-ttu-id="e56c4-236">00000001</span><span class="sxs-lookup"><span data-stu-id="e56c4-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="e56c4-237">Нажмите кнопку **OK**, чтобы сохранить изменения, затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="e56c4-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="e56c4-238">Далее вам потребуется связать созданный объект групповой политики с группой пользователей, которым требуется назначить политику, например, с подразделением.</span><span class="sxs-lookup"><span data-stu-id="e56c4-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="e56c4-239">Использование объекта групповой политики для назначения политики</span><span class="sxs-lookup"><span data-stu-id="e56c4-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="e56c4-240">В консоли управления групповой политики щелкните правой кнопкой мыши подразделение, которому требуется назначить политику, затем выберите **Link to an existing GPO** (Связать с существующим объектом групповой политики).</span><span class="sxs-lookup"><span data-stu-id="e56c4-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="e56c4-241">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="e56c4-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="e56c4-242">На целевом компьютере пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e56c4-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="e56c4-243">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e56c4-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="e56c4-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="e56c4-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="e56c4-245">Под строкой Assigned Group Policy Objects (Назначенные объекты групповой политики) должно отображаться имя созданного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="e56c4-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="e56c4-p115">Вы также можете убедиться, что объект групповой политики успешно обновил реестр на компьютере пользователя, проверив реестр. Откройте редактор реестра и перейдите к ключу **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Если объект групповой политики успешно обновил реестр, параметр EnableSkypeUI будет иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="e56c4-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

