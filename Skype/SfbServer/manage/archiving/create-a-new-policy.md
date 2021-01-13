---
title: Создание новой политики архива в Skype для бизнеса Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: Сводка. Узнайте, как создать новую политику архива для Skype для бизнеса Server.
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817649"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="269e5-103">Создание новой политики архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="269e5-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="269e5-104">**Сводка:** Узнайте, как создать новую политику архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="269e5-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="269e5-105">Новые политики архива можно создать с помощью панели управления или с помощью Windows PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="269e5-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="269e5-106">Создание новой политики архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="269e5-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="269e5-107">Чтобы создать новую политику архива с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="269e5-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="269e5-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="269e5-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="269e5-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="269e5-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="269e5-110">В левой панели навигации щелкните **"Мониторинг** и архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="269e5-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="269e5-111">Нажмите кнопку **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="269e5-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="269e5-112">Чтобы создать политику архива на уровне сайта, щелкните "Политика сайта", а затем в области "Выбор сайта" выберите **сайт,** к которому должна применяться политика.</span><span class="sxs-lookup"><span data-stu-id="269e5-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="269e5-113">Чтобы создать политику архивации на уровне пользователя, щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="269e5-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="269e5-114">В разделе **Новая политика архивации** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="269e5-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="269e5-115">В разделе **Имя** укажите имя новой политики (например, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="269e5-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="269e5-116">В разделе **Описание** приведены подробные сведения о том, что представляет собой политика (например, «Внешняя политика архивации на уровне пользователя для компании Contoso»).</span><span class="sxs-lookup"><span data-stu-id="269e5-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="269e5-117">Для управления архивацией операций обмена данными с внутренними пользователями установите или снимите флажок **Архивация внутренних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="269e5-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="269e5-118">Для управления архивацией операций обмена данными с внешними пользователями установите или снимите флажок **Архивация внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="269e5-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="269e5-119">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="269e5-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="269e5-120">Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="269e5-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="269e5-121">Дополнительные сведения см. в подмене политики [архива к пользователям Skype для бизнеса Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="269e5-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="269e5-122">Создание новой политики архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="269e5-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="269e5-123">Вы также можете создать новые политики архива с помощью Windows PowerShell **New-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="269e5-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="269e5-124">Дополнительные сведения см. в разделе справки по [cmdlet New-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="269e5-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="269e5-125">Создание новой политики архива на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="269e5-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="269e5-126">Данная команда создает новую политику архивации для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="269e5-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="269e5-127">Создание новой политики архива на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="269e5-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="269e5-128">Чтобы создать новую политику архива на уровне пользователя, просто укажите уникальное удостоверение при создании политики:</span><span class="sxs-lookup"><span data-stu-id="269e5-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="269e5-129">Создание новой политики архива, которая позволяет архивать сеансы внутренней связи</span><span class="sxs-lookup"><span data-stu-id="269e5-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="269e5-130">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новые политики будут использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="269e5-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="269e5-131">Чтобы создать политики, использующие другие значения свойств просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="269e5-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="269e5-132">Например, следующая команда создает политику архива, которая разрешает архивы внутренних сеансов обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="269e5-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="269e5-133">Создание новой политики архива, которая позволяет архивать как внутренние, так и внешние сеансы связи</span><span class="sxs-lookup"><span data-stu-id="269e5-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="269e5-134">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="269e5-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="269e5-135">Например, эта команда настраивает новую политику для архива внутренних и внешних сеансов обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="269e5-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
