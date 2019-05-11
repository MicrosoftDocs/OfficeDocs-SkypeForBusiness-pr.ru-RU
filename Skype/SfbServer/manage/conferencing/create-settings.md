---
title: Создание параметров конфигурации собрания в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Сводка: Сведения о создании параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: ea75e133ab15f450a6316c9ee86ba2ded485f29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919418"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9bbed-103">Создание параметров конфигурации собрания в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9bbed-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9bbed-104">**Сводка:** Сведения о создании параметров конфигурации собрания в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bbed-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9bbed-105">Можно создать параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bbed-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9bbed-106">Создание параметров конфигурации собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9bbed-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9bbed-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9bbed-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9bbed-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bbed-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9bbed-109">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="9bbed-110">На странице **Конфигурация собрания** нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9bbed-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="9bbed-p101">Чтобы создать политику уровня сайта, выберите вариант **Настройка сайта**. В поле поиска **Выбор сайта** частично или полностью введите имя сайта, для которого требуется определить параметры присоединения к собранию. В полученном списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="9bbed-p102">Чтобы создать политику уровня пула, выберите вариант **Конфигурация пула**. В поле поиска **Выбор службы** частично или полностью введите имя службы пула, для которой требуется определить параметры присоединения к собранию. В полученном списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="9bbed-p103">Чтобы направлять участников, которые присоединяются к собранию через ТСОП, в "зал ожидания", снимите флажок **Абоненты ТСОП минуют зал ожидания**. По умолчанию участники, подключающиеся из ТСОП, могут сразу присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="9bbed-119">Чтобы настроить пользователей, которые могут быть выступающими, в разделе **Назначить в качестве выступающего** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9bbed-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="9bbed-120">Чтобы запретить назначение выступающими любых пользователей кроме организатора, выберите вариант **Нет**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="9bbed-p104">Чтобы разрешить быть выступающими только сотрудникам организации, выберите вариант **Компания**. Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="9bbed-123">Чтобы разрешить всем участникам быть выступающими, выберите вариант **Все**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="9bbed-p105">Чтобы оставить организатору возможность выбора типа конференции при планировании собрания, снимите флажок **Назначаемый тип конференции по умолчанию**. По умолчанию тип конференции назначается автоматически.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="9bbed-p106">Чтобы запретить автоматическое предоставление доступа анонимным (не прошедшим проверку подлинности) пользователям, снимите флажок **Допуск анонимных пользователей по умолчанию**. По умолчанию анонимные пользователи автоматически допускаются к собраниям.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="9bbed-128">Чтобы настроить отправку участникам приглашения на собрание, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9bbed-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="9bbed-129">Обратите внимание, что максимальная длина URL-адресов и настраиваемых колонтитулов — 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="9bbed-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="9bbed-130">Если не указать значение для настроек, они не будут включены в собрание (кроме **URL-адреса справки**).</span><span class="sxs-lookup"><span data-stu-id="9bbed-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="9bbed-131">Если не включить URL-адрес справки, URL-адрес справки по умолчанию для Скайп для бизнеса отображается в приглашении на.</span><span class="sxs-lookup"><span data-stu-id="9bbed-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="9bbed-p108">Чтобы настроить логотип, который отображается в приглашении на собрание, укажите местоположение логотипа в поле **URL-адрес логотипа**. В качестве логотипа необходимо использовать изображение формата GIF или JPG, имеющее размер 188 на 30 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9bbed-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="9bbed-134">Чтобы настроить текст справки, который отображается в приглашении на собрание, введите расположение текста справки в поле **URL-адрес справки**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="9bbed-135">Чтобы настроить юридическую информацию, которая отображается в приглашении на собрание, укажите местоположение в поле **URL-адрес юридических сведений**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="9bbed-136">Чтобы настроить текст колонтитулов, которые отображаются в приглашении на собрание, введите текст в поле **Текст нижнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="9bbed-137">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9bbed-138">Создание параметров конфигурации собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="9bbed-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9bbed-139">Для создания параметров конфигурации собрания используется командлет **New-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9bbed-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="9bbed-140">Следующая команда создает новый набор параметров конфигурации собрания для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="9bbed-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="9bbed-141">Так как при выполнении предыдущей команды не были указаны никакие параметры (кроме обязательного параметра Identity), для всех свойств новых параметров конфигурации собраний будут использоваться значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9bbed-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="9bbed-p109">Для создания настроек, использующих разные значения свойств, просто добавьте соответствующий параметр и значение параметра. Например, чтобы создать коллекцию параметров конфигурации собраний, которые по умолчанию допускают выступление всех участников на собрании, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9bbed-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="9bbed-p110">Многочисленные значения свойств можно задать путем включения различных параметров. Например, следующая команда допускает выступление любого участника на собрании, а также переводит пользователей ТСОП в зал ожидания до их официального допуска к участию в собрании:</span><span class="sxs-lookup"><span data-stu-id="9bbed-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="9bbed-146">Дополнительные сведения, включая полный список параметров содержатся в разделе [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9bbed-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

