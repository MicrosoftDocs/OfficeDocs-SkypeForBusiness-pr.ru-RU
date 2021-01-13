---
title: Создание параметров конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: Сводка. Сведения о создании параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: edc498ed3847618b17970fb2270c21fd3f4ec025
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828209"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1b2a7-103">Создание параметров конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1b2a7-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1b2a7-104">**Сводка:** Узнайте, как создавать параметры конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1b2a7-105">Параметры конфигурации собраний можно создать с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1b2a7-106">Создание параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1b2a7-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1b2a7-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1b2a7-108">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1b2a7-109">В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**</span><span class="sxs-lookup"><span data-stu-id="1b2a7-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="1b2a7-110">На странице **конфигурации собрания** нажмите **New (Создать)**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="1b2a7-p101">Чтобы создать политику на уровне узла, выберите пункт **Site configuration (Конфигурация узла)**. В поле поиска **Select a Site (Выбор узла)** введите имя (или часть имени) узла, для которого требуется определить параметры присоединения к собранию. В появившемся списке узлов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="1b2a7-p102">Чтобы создать политику уровня пула, выберите вариант **Pool configuration** (Настройка пула). В поле поиска **Выберите службу** введите часть или полное имя службы пула, для которой требуется определить параметры присоединения к собранию. В полученном списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="1b2a7-p103">Чтобы направлять участников, которые присоединяются к собранию через ТСОП, в "зал ожидания", снимите флажок **PSTN callers bypass lobby** (Обход "зала ожидания" для абонентов ТСОП). По умолчанию участники, подключающиеся из ТСОП, могут сразу присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="1b2a7-119">Чтобы настроить пользователей, которые могут быть выступающими, в разделе **Designate as presenter** (Назначить выступающим) выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="1b2a7-120">Чтобы запретить назначение выступающими любых пользователей кроме организатора, выберите вариант **Нет**.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="1b2a7-p104">Чтобы разрешить быть выступающими только сотрудникам организации, выберите вариант **Компания**. Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="1b2a7-123">Чтобы разрешить всем участникам быть выступающими, выберите вариант **Все**.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="1b2a7-p105">Чтобы настроить для организатора возможность выбора типа конференции при планировании собрания, снимите флажок **Assigned conference type by default** (Назначение типа конференции по умолчанию). По умолчанию тип конференции назначается автоматически.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="1b2a7-p106">Чтобы запретить автоматическое предоставление доступа анонимным (не прошедшим проверку подлинности) пользователям, снимите флажок **Admit anonymous users by default** (Допускать анонимных пользователей по умолчанию). По умолчанию анонимные пользователи автоматически допускаются к собраниям.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="1b2a7-128">Чтобы настроить приглашение на собрание, которое отправляется участникам, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="1b2a7-129">Обратите внимание, что максимальная длина URL-адресов и текста пользовательского footer составляет 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="1b2a7-130">За **исключением URL-адреса** справки, если не указать значение для настроек, они не будут включены в собрание.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="1b2a7-131">Если не включить настраиваемый URL-адрес справки, в приглашении будет отображаться URL-адрес справки по умолчанию для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="1b2a7-132">Чтобы настроить логотип, который отображается в приглашении на собрание, в URL-адресе логотипа введите расположение логотипа.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="1b2a7-133">Логотип должен быть изображением GIF или JPG размером 188 на 30 пикселей.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="1b2a7-134">Чтобы настроить текст справки, который отображается в приглашении на собрание, **в** URL-адресе справки введите расположение текста справки.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="1b2a7-135">Чтобы настроить юридический текст, который отображается в приглашении на собрание, введите расположение юридического текста в URL-адресе юридического текста.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="1b2a7-136">Чтобы настроить текст footer, который отображается в приглашении на собрание, в тексте пользовательского **footer** введите текст.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="1b2a7-137">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1b2a7-138">Создание параметров конфигурации собраний с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1b2a7-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1b2a7-139">Чтобы создать параметры конфигурации собраний, используйте **cmdlet New-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="1b2a7-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="1b2a7-140">Следующая команда создает новый набор параметров конфигурации собраний для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="1b2a7-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="1b2a7-141">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в предыдущей команде, новые параметры конфигурации собрания будут использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="1b2a7-142">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="1b2a7-143">Например, чтобы создать коллекцию параметров конфигурации собраний, которые по умолчанию допускают всех к собранию в качестве presenter, используйте данная команда:</span><span class="sxs-lookup"><span data-stu-id="1b2a7-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="1b2a7-144">Несколько значений свойств можно установить, включив несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="1b2a7-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="1b2a7-145">Например, следующая команда допускает всех участников собрания в качестве presenter, а также заставляет пользователей PSTN ждать в "ожиданиях" до тех пор, пока они не будут официально допущены к собранию:</span><span class="sxs-lookup"><span data-stu-id="1b2a7-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="1b2a7-146">Дополнительные сведения, включая полный список параметров, см. в подстроке [New-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1b2a7-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

