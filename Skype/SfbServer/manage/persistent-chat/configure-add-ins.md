---
title: Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Сводка: Сведения о настройке надстроек для комнат чата Persistent Chat Server в Скайп для Business Server 2015.'
ms.openlocfilehash: dbd1eba6cf73783d02b502930f271ada93e28145
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="55fa5-103">Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="55fa5-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55fa5-104">**Сводка:** Сведения о настройке надстроек для комнат чата Persistent Chat Server в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="55fa5-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="55fa5-105">Надстройки используются для расширения доступных в комнате возможностей с помощью сопоставления URL-адресов с комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="55fa5-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="55fa5-106">Эти URL-адреса отображаются в области расширения беседы чата клиента.</span><span class="sxs-lookup"><span data-stu-id="55fa5-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="55fa5-107">Типичная надстройки могут содержать URL-адрес приложение Silverlight, перехватывает при Финансовый символ представляется чата и отображает журнал запасов в области расширяемости.</span><span class="sxs-lookup"><span data-stu-id="55fa5-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="55fa5-108">К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — "Важные размышления" или "Тема дня".</span><span class="sxs-lookup"><span data-stu-id="55fa5-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="55fa5-109">Чтобы пользователи увидели надстройку в клиенте, необходимо добавить надстройку в список зарегистрированных надстроек, а руководители или создатели комнат чата должны сопоставить комнаты с надстройкой</span><span class="sxs-lookup"><span data-stu-id="55fa5-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="55fa5-110">Конфигурация надстроек для комнат чата с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="55fa5-110">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="55fa5-111">Чтобы настроить надстройки для комнат чата с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="55fa5-111">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="55fa5-112">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="55fa5-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55fa5-113">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="55fa5-113">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="55fa5-114">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="55fa5-114">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="55fa5-115">Для нескольких развертываний пул серверов сохраняемого чата выберите соответствующий пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="55fa5-115">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="55fa5-116">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="55fa5-116">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="55fa5-117">В списке **поле выбора службы**выберите службы, соответствующий пул серверов сохраняемого чата, где необходимо создать надстройку.</span><span class="sxs-lookup"><span data-stu-id="55fa5-117">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="55fa5-118">Надстройки нельзя перемещать из одного пула в другой или совместно использовать разными пулами.</span><span class="sxs-lookup"><span data-stu-id="55fa5-118">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="55fa5-119">В окне **Новая надстройка** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="55fa5-119">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="55fa5-120">В поле **Имя** укажите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="55fa5-120">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="55fa5-p103">В поле **URL-адрес** укажите URL-адрес, который должен быть сопоставлен с данной надстройкой. Эти URL-адреса ограничены протоколами HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="55fa5-p103">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="55fa5-123">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="55fa5-123">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="55fa5-124">Конфигурация надстроек с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55fa5-124">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="55fa5-125">Надстройки для комнат чата можно настроить с помощью следующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55fa5-125">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="55fa5-126">Для получения дополнительных сведений о синтаксисе, включая все доступные параметры просмотра [Скайп оболочки управления 2015 Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="55fa5-126">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
<span data-ttu-id="55fa5-127">| |</span><span class="sxs-lookup"><span data-stu-id="55fa5-127"></span></span>
|<span data-ttu-id="55fa5-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="55fa5-128">**Cmdlet**</span></span>|<span data-ttu-id="55fa5-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="55fa5-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55fa5-130">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="55fa5-130">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="55fa5-131">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-131">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="55fa5-132">Командлет Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="55fa5-132">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="55fa5-133">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-133">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="55fa5-134">Командлет Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="55fa5-134">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="55fa5-135">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="55fa5-135">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="55fa5-136">Командлет remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="55fa5-136">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="55fa5-137">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-137">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="55fa5-138">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-138">Create a new add-in</span></span>

<span data-ttu-id="55fa5-139">Создание надстройки можно создать с помощью командлета **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="55fa5-139">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="55fa5-140">Например следующая команда создает новый надстройки (с именем ITPersistentChatAddin) для пула atl-cs-001.contoso.com. Параметр URL-адреса и значение параметра http://atl-cs-001.contoso.com/itchat указать расположение добавить в веб-страницы:</span><span class="sxs-lookup"><span data-stu-id="55fa5-140">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com. The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="55fa5-141">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-141">Configure settings for an existing add-in</span></span>

<span data-ttu-id="55fa5-142">Параметры для существующей надстройки можно настроить с помощью командлета **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="55fa5-142">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="55fa5-143">Например, следующая команда используется для изменения URL-адреса, назначенного надстройке сохраняемого чата ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="55fa5-143">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="55fa5-144">В этом случае URL-адрес изменяется наhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="55fa5-144">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="55fa5-145">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="55fa5-145">Retrieve information about add-ins</span></span>

<span data-ttu-id="55fa5-p106">Получить информацию о надстройках можно с помощью командлета **Get-CsPersistentChatAddin**. Например, следующая команда используется для получения информации обо всех настроенных в организации надстройках сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="55fa5-p106">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="55fa5-148">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="55fa5-148">Remove an add-in</span></span>

<span data-ttu-id="55fa5-149">Add-in можно удалить с помощью командлета **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="55fa5-149">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="55fa5-150">Например, следующая команда используется для удаления надстройки сохраняемого чата ITChatAddin, найденной в пуле atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="55fa5-150">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


