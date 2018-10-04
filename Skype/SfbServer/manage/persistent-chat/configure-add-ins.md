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
ms.openlocfilehash: 4fe6c5fa15118949bd559ddb280ddf56fe41b360
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372701"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="2290e-103">Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2290e-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2290e-104">**Сводка:** Сведения о настройке надстроек для комнат чата Persistent Chat Server в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2290e-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2290e-105">Надстройки используются для расширения доступных в комнате возможностей с помощью сопоставления URL-адресов с комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="2290e-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="2290e-106">Эти URL-адреса отображаются в области расширения беседы чата клиента.</span><span class="sxs-lookup"><span data-stu-id="2290e-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="2290e-107">Типичная надстройки могут содержать URL-адрес приложение Silverlight, перехватывает при Финансовый символ представляется чата и отображает журнал запасов в области расширяемости.</span><span class="sxs-lookup"><span data-stu-id="2290e-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="2290e-108">К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — "Важные размышления" или "Тема дня".</span><span class="sxs-lookup"><span data-stu-id="2290e-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="2290e-109">Чтобы пользователи увидели надстройку в клиенте, необходимо добавить надстройку в список зарегистрированных надстроек, а руководители или создатели комнат чата должны сопоставить комнаты с надстройкой</span><span class="sxs-lookup"><span data-stu-id="2290e-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2290e-110">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2290e-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2290e-111">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="2290e-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="2290e-112">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="2290e-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="2290e-113">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2290e-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="2290e-114">Конфигурация надстроек для комнат чата с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="2290e-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="2290e-115">Чтобы настроить надстройки для комнат чата с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2290e-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="2290e-116">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="2290e-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2290e-117">Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="2290e-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2290e-118">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="2290e-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="2290e-119">Для нескольких развертываний пул серверов сохраняемого чата выберите соответствующий пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2290e-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="2290e-120">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2290e-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="2290e-121">В списке **поле выбора службы**выберите службы, соответствующий пул серверов сохраняемого чата, где необходимо создать надстройку.</span><span class="sxs-lookup"><span data-stu-id="2290e-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="2290e-122">Надстройки нельзя перемещать из одного пула в другой или совместно использовать разными пулами.</span><span class="sxs-lookup"><span data-stu-id="2290e-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="2290e-123">В окне **Новая надстройка** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2290e-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="2290e-124">В поле **Имя** укажите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="2290e-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="2290e-p104">В поле **URL-адрес** укажите URL-адрес, который должен быть сопоставлен с данной надстройкой. Эти URL-адреса ограничены протоколами HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2290e-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="2290e-127">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="2290e-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="2290e-128">Конфигурация надстроек с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2290e-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="2290e-129">Надстройки для комнат чата можно настроить с помощью следующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2290e-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2290e-130">Для получения дополнительных сведений о синтаксисе, включая все доступные параметры просмотра [Скайп оболочки управления 2015 Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="2290e-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="2290e-131">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="2290e-131">**Cmdlet**</span></span>|<span data-ttu-id="2290e-132">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2290e-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2290e-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="2290e-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="2290e-134">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="2290e-135">Командлет Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="2290e-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="2290e-136">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="2290e-137">Командлет Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="2290e-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="2290e-138">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="2290e-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="2290e-139">Командлет remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="2290e-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="2290e-140">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="2290e-141">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-141">Create a new add-in</span></span>

<span data-ttu-id="2290e-142">Создание надстройки можно создать с помощью командлета **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="2290e-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="2290e-143">Например следующая команда создает новый надстройки (с именем ITPersistentChatAddin) для пула atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2290e-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="2290e-144">Параметр URL-адреса и значение параметра http://atl-cs-001.contoso.com/itchat указать расположение добавить в веб-страницы:</span><span class="sxs-lookup"><span data-stu-id="2290e-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="2290e-145">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="2290e-146">Параметры для существующей надстройки можно настроить с помощью командлета **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="2290e-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="2290e-147">Например, следующая команда используется для изменения URL-адреса, назначенного надстройке сохраняемого чата ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="2290e-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="2290e-148">В этом случае URL-адрес изменяется наhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="2290e-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="2290e-149">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="2290e-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="2290e-p108">Получить информацию о надстройках можно с помощью командлета **Get-CsPersistentChatAddin**. Например, следующая команда используется для получения информации обо всех настроенных в организации надстройках сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="2290e-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="2290e-152">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="2290e-152">Remove an add-in</span></span>

<span data-ttu-id="2290e-153">Add-in можно удалить с помощью командлета **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="2290e-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="2290e-154">Например, следующая команда используется для удаления надстройки сохраняемого чата ITChatAddin, найденной в пуле atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="2290e-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


