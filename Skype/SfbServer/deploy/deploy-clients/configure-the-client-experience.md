---
title: Настройка взаимодействия с пользователем с помощью Скайп для бизнеса 2015
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Сводка: Сведения в этой статье описывается настройка взаимодействия с пользователем для Скайп для коммерческих пользователей.'
ms.openlocfilehash: b8d258236a5254aa1dab5e86edb9586ea514c689
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219602"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="c9952-103">Настройка взаимодействия с пользователем с помощью Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="c9952-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="c9952-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как для настройки взаимодействия с пользователем для Скайп для бизнеса 2015 пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9952-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="c9952-105">Скайп для бизнеса 2015 предоставляет нового пользовательского интерфейса, основанный на возможности использования продукта Скайп.</span><span class="sxs-lookup"><span data-stu-id="c9952-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="c9952-106">Помимо всех возможностей Lync Скайп для бизнеса предоставляет новых функций с помощью знакомых значки и упрощенный элементов управления.</span><span class="sxs-lookup"><span data-stu-id="c9952-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="c9952-107">Подробные сведения о новых возможностей клиента видеть [Изучите Скайп для бизнеса](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="c9952-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="c9952-108">Скайп для Business Server поддерживает новые Скайп для взаимодействия с пользователем предприятия, а также с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="c9952-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="c9952-109">Администратор может выбрать для пользователей предпочтительный режим взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c9952-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="c9952-110">Например требуется развернуть с клиентом Lync, пока в новый Скайп для бизнеса программой полностью обученные пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c9952-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="c9952-111">Или, если вы еще не был обновлен всех пользователей к Скайп для Business Server, можно включить все пользователи иметь тот же интерфейс клиента, пока все будут обновлены на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="c9952-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9952-112">Если ваша организация имеет оба Скайп для Business Server и развертывания Lync Server, с клиентом по умолчанию будут отличаться в зависимости от версии сервера и параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9952-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="c9952-113">Когда пользователи запуска Скайп для бизнеса в первый раз, они всегда будет видеть Скайп для бизнеса пользовательского интерфейса — даже в том случае, если вы выбрали с клиентом Lync.</span><span class="sxs-lookup"><span data-stu-id="c9952-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="c9952-114">Через несколько минут Чтобы переключиться в режим Lync запрос пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9952-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="c9952-115">Дополнительные сведения см. в разделе **Режим работы клиента при первом запуске** далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c9952-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9952-116">С клиентом Lync 2013 недоступно для Скайп для версий клиента Business 2016 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c9952-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="c9952-117">Перед настройкой клиентской среды на использование клиента Lync 2013 убедитесь, что версия клиента не начинается с цифр "16" (например: 16.x.x.x).</span><span class="sxs-lookup"><span data-stu-id="c9952-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="c9952-118">Настройка взаимодействия с клиентом</span><span class="sxs-lookup"><span data-stu-id="c9952-118">Configure the client experience</span></span>

<span data-ttu-id="c9952-119">Командлет **Set-CSClientPolicy** с параметром EnableSkypeUI позволяет настроить взаимодействие с клиентом для пользователей в организации:</span><span class="sxs-lookup"><span data-stu-id="c9952-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="c9952-120">Здесь XdsIdentity означает глобальную политику или именованную политику сайта.</span><span class="sxs-lookup"><span data-stu-id="c9952-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="c9952-121">Следующая команда выбирает Скайп для взаимодействия с пользователем предприятия для всех пользователей в вашей организации, влияет на глобальную политику (Помните, что сайт или пользовательская политики переопределить глобальную политику):</span><span class="sxs-lookup"><span data-stu-id="c9952-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="c9952-122">Следующей команды выбирает с клиентом Lync для всех пользователей в вашей организации, влияет на глобальной политики:</span><span class="sxs-lookup"><span data-stu-id="c9952-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="c9952-123">Далее команда выбирает Скайп для взаимодействия с пользователем предприятия для всех пользователей на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="c9952-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="c9952-124">Для настройки взаимодействия с пользователем для конкретных пользователей в организации можно создать новую политику пользователя с помощью командлета **New-CsClientPolicy** и назначьте политики к определенным пользователям с помощью **Grant-CsClientPolicy** командлет.</span><span class="sxs-lookup"><span data-stu-id="c9952-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c9952-125">К примеру следующая команда создает новую политику клиента, SalesClientUI, которая выбирает Скайп для взаимодействия с пользователем бизнес:</span><span class="sxs-lookup"><span data-stu-id="c9952-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="c9952-126">При выполнении следующей команды политика SalesClientUI назначается всем участникам из отдела продаж:</span><span class="sxs-lookup"><span data-stu-id="c9952-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="c9952-127">Режим работы клиента при первом запуске</span><span class="sxs-lookup"><span data-stu-id="c9952-127">First launch client behaviors</span></span>

<span data-ttu-id="c9952-128">По умолчанию когда пользователи запуска Скайп для бизнеса 2015 в первый раз, они всегда будет видеть Скайп для бизнеса пользовательского интерфейса — даже в том случае, если вы выбрали с клиентом Lync, указав значение для параметра EnableSkypeUI значение $False, как описано ранее.</span><span class="sxs-lookup"><span data-stu-id="c9952-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="c9952-129">Через несколько минут пользователям будет предложено переключиться в режим Lync.</span><span class="sxs-lookup"><span data-stu-id="c9952-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="c9952-130">Чтобы отобразить интерфейс Lync при первом запуске клиента Skype для бизнеса, выполните следующие действия до того, как клиент будет запущен в первый раз после обновления.</span><span class="sxs-lookup"><span data-stu-id="c9952-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="c9952-131">Убедитесь, что значение `EnableSkypeUI` задано значение $False в политике, с помощью как описано выше.</span><span class="sxs-lookup"><span data-stu-id="c9952-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="c9952-p106">Обновите системный реестр на компьютере пользователя. Это необходимо сделать до первого запуска клиента Skype для бизнеса. Действие выполняется всего один раз. Сведения о создании объекта групповой политики для обновления реестра на присоединенном к домену компьютере см. далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c9952-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="c9952-135">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** создайте новое **двоичное** значение.</span><span class="sxs-lookup"><span data-stu-id="c9952-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="c9952-136">**Имя значения** должно быть **EnableSkypeUI**. Для **данных значения** задайте **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="c9952-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="c9952-137">Строка должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c9952-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="c9952-138">Теперь интерфейс Lync будет отображаться при первом запуске клиента Skype для бизнеса пользователями.</span><span class="sxs-lookup"><span data-stu-id="c9952-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="c9952-139">Руководство по управлению отображением экрана приветствия</span><span class="sxs-lookup"><span data-stu-id="c9952-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="c9952-140">При открытии Скайп для клиента Business, поведение по умолчанию — Показать экран приветствия, который включает в себя *7 советы запрашивать большинство пользователей*.</span><span class="sxs-lookup"><span data-stu-id="c9952-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="c9952-141">Можно отключить отображение экран приветствия, но дать пользователям получать доступ к учебника по, добавив следующий параметр реестра на клиентском компьютере:</span><span class="sxs-lookup"><span data-stu-id="c9952-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="c9952-p108">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новый **Параметр DWORD (32-разрядный)**. Для параметра **Имя значение** необходимо указать значение **IsBasicTutorialSeenByUser**, для параметра **Данные значения** — **1**.</span><span class="sxs-lookup"><span data-stu-id="c9952-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="c9952-144">Ключ должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c9952-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="c9952-145">Отключение руководства в клиенте</span><span class="sxs-lookup"><span data-stu-id="c9952-145">Turn off the client tutorial</span></span>

<span data-ttu-id="c9952-146">Чтобы ваши пользователи не могли получить доступ к руководству, отключите руководство клиента с помощью следующего значения реестра:</span><span class="sxs-lookup"><span data-stu-id="c9952-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="c9952-p109">В ключе **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** создайте новый **Параметр DWORD (32-разрядный)**. Для параметра **Имя значение** необходимо указать значение **TutorialFeatureEnabled**, для параметра **Данные значения** — **0**.</span><span class="sxs-lookup"><span data-stu-id="c9952-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="c9952-149">Lync</span><span class="sxs-lookup"><span data-stu-id="c9952-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="c9952-150">Вы можете вернуть доступ к руководству, присвоив параметру **Данные значения** значение **1**.</span><span class="sxs-lookup"><span data-stu-id="c9952-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="c9952-151">Режимы работы клиента по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9952-151">Default client behaviors</span></span>

<span data-ttu-id="c9952-152">Если ваша организация имеет оба Скайп для Business Server и развертывания Lync Server, с клиентом будут отличаться в зависимости от версии сервера и пользовательский Интерфейс Скайп установка.</span><span class="sxs-lookup"><span data-stu-id="c9952-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="c9952-153">В следующей таблице указан первоначальный режим взаимодействия с клиентом в зависимости от версии сервера и параметра пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9952-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="c9952-154">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="c9952-154">**Server version**</span></span>|<span data-ttu-id="c9952-155">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="c9952-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="c9952-156">**Взаимодействие с клиентом**</span><span class="sxs-lookup"><span data-stu-id="c9952-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9952-157">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c9952-157">Skype for Business Server</span></span> |<span data-ttu-id="c9952-158">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9952-158">Default</span></span>  <br/> |<span data-ttu-id="c9952-159">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c9952-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="c9952-160">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c9952-160">Skype for Business Server</span></span>  |<span data-ttu-id="c9952-161">True</span><span class="sxs-lookup"><span data-stu-id="c9952-161">True</span></span>  <br/> |<span data-ttu-id="c9952-162">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c9952-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="c9952-163">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c9952-163">Skype for Business Server</span></span>  |<span data-ttu-id="c9952-164">False</span><span class="sxs-lookup"><span data-stu-id="c9952-164">False</span></span>  <br/> |<span data-ttu-id="c9952-165">Пользователь запрос на переключение в режим Lync (пользователя могут переключаться между Скайп для бизнеса более поздней версии Чтобы изменить параметр пользовательского интерфейса значение $true)</span><span class="sxs-lookup"><span data-stu-id="c9952-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="c9952-166">Lync Server 2010 или Lync Server 2013 (с правильный исправления)</span><span class="sxs-lookup"><span data-stu-id="c9952-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="c9952-167">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9952-167">Default</span></span>  <br/> |<span data-ttu-id="c9952-168">Пользователь запрос на переключение в режим Lync (пользователя могут переключаться между Скайп для бизнеса более поздней версии Чтобы изменить параметр пользовательского интерфейса значение $true)</span><span class="sxs-lookup"><span data-stu-id="c9952-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="c9952-169">Lync Server 2010 или Lync Server 2013 (с правильный исправления)</span><span class="sxs-lookup"><span data-stu-id="c9952-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="c9952-170">True</span><span class="sxs-lookup"><span data-stu-id="c9952-170">True</span></span>  <br/> |<span data-ttu-id="c9952-171">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c9952-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="c9952-172">Lync Server 2010 или Lync Server 2013 (с правильный исправления)</span><span class="sxs-lookup"><span data-stu-id="c9952-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="c9952-173">False</span><span class="sxs-lookup"><span data-stu-id="c9952-173">False</span></span>  <br/> |<span data-ttu-id="c9952-174">Пользователь запрос на переключение в режим Lync (пользователя могут переключаться между Скайп для бизнеса более поздней версии Чтобы изменить параметр пользовательского интерфейса значение $true)</span><span class="sxs-lookup"><span data-stu-id="c9952-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="c9952-175">Lync Server 2010 или Lync Server 2013 (без обновления)</span><span class="sxs-lookup"><span data-stu-id="c9952-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="c9952-176">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9952-176">Default</span></span>  <br/> |<span data-ttu-id="c9952-177">Пользователь запрос на переключение в режим Lync (пользователь не может переключить Скайп для бизнеса более поздней версии)</span><span class="sxs-lookup"><span data-stu-id="c9952-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="c9952-178">В следующей таблице показаны с клиентом, когда администратор изменяет начальный параметр для взаимодействия Скайп пользовательского интерфейса:</span><span class="sxs-lookup"><span data-stu-id="c9952-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="c9952-179">**Версия сервера**</span><span class="sxs-lookup"><span data-stu-id="c9952-179">**Server version**</span></span>|<span data-ttu-id="c9952-180">**Параметр EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="c9952-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="c9952-181">**Пользовательский Интерфейс клиента = Lync**</span><span class="sxs-lookup"><span data-stu-id="c9952-181">**Client UI = Lync**</span></span>|<span data-ttu-id="c9952-182">**Клиентский пользовательский интерфейс = Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="c9952-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9952-183">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c9952-183">Skype for Business Server</span></span> |<span data-ttu-id="c9952-184">True</span><span class="sxs-lookup"><span data-stu-id="c9952-184">True</span></span>  <br/> |<span data-ttu-id="c9952-185">Пользователь, чтобы переключиться на Скайп для бизнеса и ответы</span><span class="sxs-lookup"><span data-stu-id="c9952-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="c9952-186">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c9952-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="c9952-187">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c9952-187">Skype for Business Server</span></span> |<span data-ttu-id="c9952-188">False</span><span class="sxs-lookup"><span data-stu-id="c9952-188">False</span></span>  <br/> |<span data-ttu-id="c9952-189">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="c9952-189">Lync mode</span></span>  <br/> |<span data-ttu-id="c9952-190">Запрос на переключение в режим Lync пользователя</span><span class="sxs-lookup"><span data-stu-id="c9952-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="c9952-191">Lync Server 2010 или Lync Server 2013 (с правильный исправления)</span><span class="sxs-lookup"><span data-stu-id="c9952-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="c9952-192">True</span><span class="sxs-lookup"><span data-stu-id="c9952-192">True</span></span>  <br/> |<span data-ttu-id="c9952-193">Пользователь, чтобы переключиться на Скайп для бизнеса и ответы</span><span class="sxs-lookup"><span data-stu-id="c9952-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="c9952-194">Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c9952-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="c9952-195">Lync Server 2010 или Lync Server 2013 (с правильный исправления)</span><span class="sxs-lookup"><span data-stu-id="c9952-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="c9952-196">False</span><span class="sxs-lookup"><span data-stu-id="c9952-196">False</span></span>  <br/> |<span data-ttu-id="c9952-197">Режим Lync</span><span class="sxs-lookup"><span data-stu-id="c9952-197">Lync mode</span></span>  <br/> |<span data-ttu-id="c9952-198">Запрос на переключение в режим Lync пользователя</span><span class="sxs-lookup"><span data-stu-id="c9952-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="c9952-199">Lync Server 2010 или Lync Server 2013 (без обновления)</span><span class="sxs-lookup"><span data-stu-id="c9952-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="c9952-200">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="c9952-200">Default</span></span>  <br/> |<span data-ttu-id="c9952-201">Режим Lync (не могут переключиться на Скайп для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="c9952-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="c9952-202">Режим Lync (не могут переключиться на Скайп для бизнеса)</span><span class="sxs-lookup"><span data-stu-id="c9952-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="c9952-203">Версия исправления, необходимые для управления конфигурацией Скайп для клиента Business являются:</span><span class="sxs-lookup"><span data-stu-id="c9952-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="c9952-204">Lync Server 2010 — накопительное обновление за февраль 2015 (4.0.7577.710) для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c9952-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="c9952-205">Сведения в статье [обновления для Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="c9952-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="c9952-206">Lync Server 2013 — накопительное обновление за декабрь 2014 г (5.0.8308.857) для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9952-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="c9952-207">Сведения в статье [обновления для Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="c9952-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="c9952-208">Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену</span><span class="sxs-lookup"><span data-stu-id="c9952-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="c9952-209">Обновление реестра для отображения взаимодействия с пользователем Lync первый раз, пользователь запускает Скайп для клиента Business 2015 должно выполняться только один раз.</span><span class="sxs-lookup"><span data-stu-id="c9952-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="c9952-210">Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения, а не обновлять данные значения.</span><span class="sxs-lookup"><span data-stu-id="c9952-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="c9952-211">Если при применении GPO новое значение не существует, оно будет создано, а для данных значения будет задано значение 0.</span><span class="sxs-lookup"><span data-stu-id="c9952-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="c9952-212">Следующая процедура описывается изменение реестра для отображения с клиентом Lync первый раз, пользователь запускает Скайп для клиента Business 2015.</span><span class="sxs-lookup"><span data-stu-id="c9952-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="c9952-213">Эту процедуру можно также использовать для того, чтобы отключить руководство на экране приветствия, как было описано ранее.</span><span class="sxs-lookup"><span data-stu-id="c9952-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="c9952-214">Создание GPO</span><span class="sxs-lookup"><span data-stu-id="c9952-214">To create the GPO</span></span>

1. <span data-ttu-id="c9952-215">Запустите **Консоль управления групповыми политиками**.</span><span class="sxs-lookup"><span data-stu-id="c9952-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="c9952-216">Сведения о работе с консолью управления групповыми политиками см. в разделе [Консоль управления групповыми политиками](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="c9952-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="c9952-217">Щелкните правой кнопкой мыши узел **Объекты групповой политики** и выберите в меню пункт **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c9952-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="c9952-218">В диалоговом окне **Новый объект групповой политики** введите название объекта, напримерMakeLyncDefaultUI, затем нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9952-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="c9952-219">Щелкните правой кнопкой мыши только что созданный объект групповой политики и выберите в меню пункт **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="c9952-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="c9952-220">В **Редакторе управления групповыми политиками** разверните папки **Конфигурация пользователя**, **Параметры**, **Параметры Windows** и выберите узел **Реестр**.</span><span class="sxs-lookup"><span data-stu-id="c9952-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="c9952-221">Щелкните правой кнопкой мыши на узле **Реестр** и выберите **Создать** > **Элемент реестра**.</span><span class="sxs-lookup"><span data-stu-id="c9952-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="c9952-222">В диалоговом окне **Новые свойства реестра** обновите следующие поля.</span><span class="sxs-lookup"><span data-stu-id="c9952-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="c9952-223">**Поле**</span><span class="sxs-lookup"><span data-stu-id="c9952-223">**Field**</span></span>|<span data-ttu-id="c9952-224">**Значение для выбора или ввода**</span><span class="sxs-lookup"><span data-stu-id="c9952-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c9952-225">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c9952-225">**Action**</span></span> <br/> |<span data-ttu-id="c9952-226">**Создание**</span><span class="sxs-lookup"><span data-stu-id="c9952-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="c9952-227">**Куст**</span><span class="sxs-lookup"><span data-stu-id="c9952-227">**Hive**</span></span> <br/> | <span data-ttu-id="c9952-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="c9952-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="c9952-229">**Ключевой путь**</span><span class="sxs-lookup"><span data-stu-id="c9952-229">**Key Path**</span></span> <br/> |<span data-ttu-id="c9952-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="c9952-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="c9952-231">**Имя значения**</span><span class="sxs-lookup"><span data-stu-id="c9952-231">**Value name**</span></span> <br/> |<span data-ttu-id="c9952-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="c9952-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="c9952-233">**Тип значения**</span><span class="sxs-lookup"><span data-stu-id="c9952-233">**Value type**</span></span> <br/> |<span data-ttu-id="c9952-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="c9952-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="c9952-235">**Данные значения**</span><span class="sxs-lookup"><span data-stu-id="c9952-235">**Value data**</span></span> <br/> |<span data-ttu-id="c9952-236">00000000</span><span class="sxs-lookup"><span data-stu-id="c9952-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="c9952-237">Нажмите кнопку **OK**, чтобы сохранить изменения, затем закройте объект групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c9952-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="c9952-238">Далее вам потребуется связать созданный объект групповой политики с группой пользователей, которым требуется назначить политику, например, с подразделением.</span><span class="sxs-lookup"><span data-stu-id="c9952-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="c9952-239">Использование объекта групповой политики для назначения политики</span><span class="sxs-lookup"><span data-stu-id="c9952-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="c9952-240">В консоли управления групповой политики щелкните правой кнопкой мыши подразделение, которому требуется назначить политику, затем выберите **Link to an existing GPO** (Связать с существующим объектом групповой политики).</span><span class="sxs-lookup"><span data-stu-id="c9952-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="c9952-241">В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9952-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="c9952-242">На целевом компьютере пользователя откройте командную строку и введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c9952-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="c9952-243">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c9952-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="c9952-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="c9952-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="c9952-245">Под строкой Assigned Group Policy Objects (Назначенные объекты групповой политики) должно отображаться имя созданного объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c9952-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="c9952-p115">Вы также можете убедиться, что объект групповой политики успешно обновил реестр на компьютере пользователя, проверив реестр. Откройте редактор реестра и перейдите к ключу **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Если объект групповой политики успешно обновил реестр, параметр EnableSkypeUI будет иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="c9952-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

