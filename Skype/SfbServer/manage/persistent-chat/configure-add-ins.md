---
title: Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Сводка: сведения о том, как настроить надстройки для сохраняемого чата-помещения на сервер чатов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 01e58422f28d0027114f5bc424f01eb9ef3d9e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817295"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="61f3f-103">Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="61f3f-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61f3f-104">**Сводка:** Сведения о том, как настроить надстройки для сохраняемого чата-подключения к серверным комнатам в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61f3f-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61f3f-105">Надстройки используются для расширения доступных в комнате возможностей с помощью сопоставления URL-адресов с комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="61f3f-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="61f3f-106">Эти URL-адреса отображаются в области расширения беседы чата клиента.</span><span class="sxs-lookup"><span data-stu-id="61f3f-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="61f3f-107">Типичная надстройка может включать URL-адрес, указывающий на приложение Silverlight, которое перехватывается, когда Биржевая сводка размещается в комнате чата, и на панели расширяемости отображается история акций.</span><span class="sxs-lookup"><span data-stu-id="61f3f-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="61f3f-108">К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — "Важные размышления" или "Тема дня".</span><span class="sxs-lookup"><span data-stu-id="61f3f-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="61f3f-109">Чтобы пользователи увидели надстройку в клиенте, необходимо добавить надстройку в список зарегистрированных надстроек, а руководители или создатели комнат чата должны сопоставить комнаты с надстройкой</span><span class="sxs-lookup"><span data-stu-id="61f3f-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61f3f-110">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="61f3f-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="61f3f-111">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="61f3f-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="61f3f-112">Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="61f3f-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="61f3f-113">Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61f3f-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="61f3f-114">Конфигурация надстроек для комнат чата с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="61f3f-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="61f3f-115">Чтобы настроить надстройки для комнат чата с помощью панели управления, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61f3f-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="61f3f-116">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="61f3f-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="61f3f-117">В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="61f3f-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="61f3f-118">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Надстройка**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="61f3f-119">Для нескольких развертываний пула серверов с постоянным подключением выберите нужный пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="61f3f-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="61f3f-120">На странице **Надстройка** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="61f3f-121">В окне **Выбор службы**выберите службу, соответствующую пулу серверов сохраняемого чата, в котором необходимо создать надстройку.</span><span class="sxs-lookup"><span data-stu-id="61f3f-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="61f3f-122">Надстройки нельзя перемещать из одного пула в другой или совместно использовать разными пулами.</span><span class="sxs-lookup"><span data-stu-id="61f3f-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="61f3f-123">В окне **Новая надстройка** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="61f3f-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="61f3f-124">В поле **Имя** укажите имя новой надстройки.</span><span class="sxs-lookup"><span data-stu-id="61f3f-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="61f3f-p104">В поле **URL-адрес** укажите URL-адрес, который должен быть сопоставлен с данной надстройкой. Эти URL-адреса ограничены протоколами HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="61f3f-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="61f3f-127">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="61f3f-128">Конфигурация надстроек с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61f3f-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="61f3f-p105">Надстройки для комнат чата можно настроить с помощью следующих командлетов Windows PowerShell. Дополнительные сведения о синтаксисе, включая все доступные параметры, см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="61f3f-p105">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets. For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="61f3f-131">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="61f3f-131">**Cmdlet**</span></span>|<span data-ttu-id="61f3f-132">**Описание**</span><span class="sxs-lookup"><span data-stu-id="61f3f-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61f3f-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61f3f-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61f3f-134">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="61f3f-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61f3f-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61f3f-136">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="61f3f-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61f3f-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61f3f-138">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="61f3f-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="61f3f-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61f3f-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61f3f-140">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="61f3f-141">Создание новой надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-141">Create a new add-in</span></span>

<span data-ttu-id="61f3f-142">Вы можете создать новую надстройку с помощью командлета **New-ксперсистентчатаддин** .</span><span class="sxs-lookup"><span data-stu-id="61f3f-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="61f3f-143">Например, следующая команда создает новую надстройку (с именем Итперсистентчатаддин) для пула atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="61f3f-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="61f3f-144">Параметр URL-адреса и значение http://atl-cs-001.contoso.com/itchat параметра определяют расположение веб-страницы надстройки.</span><span class="sxs-lookup"><span data-stu-id="61f3f-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="61f3f-145">Настройка параметров для существующей надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="61f3f-146">Параметры для существующей надстройки можно настроить с помощью командлета **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="61f3f-147">Например, следующая команда используется для изменения URL-адреса, назначенного надстройке сохраняемого чата ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="61f3f-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="61f3f-148">В этом случае URL-адрес изменится наhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="61f3f-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="61f3f-149">Извлечение информации о надстройках</span><span class="sxs-lookup"><span data-stu-id="61f3f-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="61f3f-p108">Получить информацию о надстройках можно с помощью командлета **Get-CsPersistentChatAddin**. Например, следующая команда используется для получения информации обо всех настроенных в организации надстройках сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="61f3f-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="61f3f-152">Удаление надстройки</span><span class="sxs-lookup"><span data-stu-id="61f3f-152">Remove an add-in</span></span>

<span data-ttu-id="61f3f-153">Вы можете удалить надстройку с помощью командлета **Remove-ксперсистентчатаддин** .</span><span class="sxs-lookup"><span data-stu-id="61f3f-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="61f3f-154">Например, следующая команда удаляет надстройку "сохраняемый чат" Итчатаддин, найденную в пуле atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="61f3f-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


