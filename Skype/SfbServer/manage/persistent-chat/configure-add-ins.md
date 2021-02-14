---
title: Настройка надстройки для комнат сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: Сводка. Узнайте, как настроить надстройки для комнат чата сервера сохраняемого чата в Skype для бизнеса Server 2015.
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815085"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="8c25d-103">Настройка надстройки для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8c25d-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8c25d-104">**Сводка:** Узнайте, как настроить надстройки для комнат чата сервера сохраняемого чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8c25d-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8c25d-105">Надстройки используются для расширения работы в комнате, связывая URL-адреса с комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="8c25d-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="8c25d-106">Эти URL-адреса отображаются в области возможностей клиентской беседы.</span><span class="sxs-lookup"><span data-stu-id="8c25d-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="8c25d-107">Типичная надстройка может включать URL-адрес, который указывает на приложение Silverlight, которое перехватывает публикацию биржевого деления в комнате чата и отображает историю акций в области возможностей.</span><span class="sxs-lookup"><span data-stu-id="8c25d-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="8c25d-108">К другим примерам относится внедрение URL-адреса OneNote 2013 в комнату чата в виде надстройки для предоставления общего контекста, например темы дня.</span><span class="sxs-lookup"><span data-stu-id="8c25d-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="8c25d-109">Прежде чем пользователи смогут увидеть надстройку в клиенте, необходимо добавить ее в список зарегистрированных надстройок, а диспетчерам комнат чата или создателям необходимо связать комнаты с надстройкой.</span><span class="sxs-lookup"><span data-stu-id="8c25d-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c25d-110">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c25d-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8c25d-111">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="8c25d-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="8c25d-112">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c25d-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="8c25d-113">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8c25d-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="8c25d-114">Настройка надстройки для комнат чата с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="8c25d-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="8c25d-115">Чтобы настроить надстройки для комнат чата с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="8c25d-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="8c25d-116">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8c25d-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8c25d-117">В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="8c25d-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8c25d-118">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="8c25d-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="8c25d-119">Для нескольких развертываний пула серверов сохраняемого чата выберите соответствующий пул в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="8c25d-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="8c25d-120">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8c25d-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="8c25d-121">В **области "Выбор службы"** выберите службу, соответствующую пулу серверов сохраняемого чата, в котором необходимо создать надстройки.</span><span class="sxs-lookup"><span data-stu-id="8c25d-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="8c25d-122">Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.</span><span class="sxs-lookup"><span data-stu-id="8c25d-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="8c25d-123">В окне **Создание надстройки** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8c25d-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="8c25d-124">В поле **Имя** введите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="8c25d-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="8c25d-125">В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой.</span><span class="sxs-lookup"><span data-stu-id="8c25d-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="8c25d-126">URL-адреса ограничены протоколами HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8c25d-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="8c25d-127">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c25d-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="8c25d-128">Настройка надстройки с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c25d-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="8c25d-129">Вы можете настроить надстройки для комнат чата с помощью следующих Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c25d-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="8c25d-130">Подробные сведения о синтаксисе, включая все доступные параметры, см. в руководстве [по skype для бизнеса Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="8c25d-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8c25d-131">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="8c25d-131">**Cmdlet**</span></span>|<span data-ttu-id="8c25d-132">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8c25d-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c25d-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="8c25d-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8c25d-134">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="8c25d-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="8c25d-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8c25d-136">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="8c25d-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="8c25d-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8c25d-138">Извлечение сведений о надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="8c25d-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="8c25d-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8c25d-140">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="8c25d-141">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-141">Create a new add-in</span></span>

<span data-ttu-id="8c25d-142">Вы можете создать новую надстройку с помощью **cmdlet New-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="8c25d-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="8c25d-143">Например, следующая команда создает новую надстройку (с именем ITPersistentChatAddin) для пула atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8c25d-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="8c25d-144">Параметр URL и его значение указывают расположение http://atl-cs-001.contoso.com/itchat веб-страницы надстройки:</span><span class="sxs-lookup"><span data-stu-id="8c25d-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="8c25d-145">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="8c25d-146">Параметры для существующей надстройки можно настроить с помощью **cmdlet Set-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="8c25d-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="8c25d-147">Например, следующая команда изменяет URL-адрес, присвоенный надстройке сохраняемого чата ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="8c25d-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="8c25d-148">В этом случае URL-адрес меняется на http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="8c25d-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="8c25d-149">Извлечение сведений о надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="8c25d-150">Сведения о надстройке можно получить с помощью **cmdlet Get-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="8c25d-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="8c25d-151">Например, следующая команда возвращает сведения обо всех надстройках сохраняемого чата, настроенных для использования в организации:</span><span class="sxs-lookup"><span data-stu-id="8c25d-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="8c25d-152">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="8c25d-152">Remove an add-in</span></span>

<span data-ttu-id="8c25d-153">Надстройку можно удалить с помощью **cmdlet Remove-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="8c25d-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="8c25d-154">Например, следующая команда удаляет надстройку сохраняемого чата ITChatAddin, найденную в пуле atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="8c25d-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


