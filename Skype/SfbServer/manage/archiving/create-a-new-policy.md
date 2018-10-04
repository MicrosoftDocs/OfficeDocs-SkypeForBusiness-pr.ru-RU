---
title: Создание новой политики архивации в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Сводка: Узнайте, как создать новую политику архивации для Скайп Business Server.'
ms.openlocfilehash: 70c955d78e6c7b259732d50c47c53e8b3bedf97c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374411"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="44b8b-103">Создание новой политики архивации в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="44b8b-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="44b8b-104">**Сводка:** Узнайте, как создание новой политики архивации Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="44b8b-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="44b8b-105">Новые политики архивации можно создавать с помощью панели управления или командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44b8b-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="44b8b-106">Создание новой политики архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="44b8b-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="44b8b-107">Порядок создания новой политики архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="44b8b-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="44b8b-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="44b8b-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="44b8b-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="44b8b-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="44b8b-110">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="44b8b-111">Нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="44b8b-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="44b8b-112">Чтобы создать политику архивации на уровне узла, выберите **Политика узла**, а затем щелкните узел, к которому должна применяться политика, в области **Выбор узла**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="44b8b-113">Чтобы создать политику архивации на уровне пользователя, щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="44b8b-114">В области **Создать политику архивации** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="44b8b-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="44b8b-115">В разделе **Имя** укажите имя новой политики (например, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="44b8b-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="44b8b-116">В разделе **Описание** приведите подробные сведения о том, что представляет собой политика (например, внешняя политика архивации на уровне пользователя для компании Contoso).</span><span class="sxs-lookup"><span data-stu-id="44b8b-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="44b8b-117">Для управления архивацией операций обмена данными с внутренними пользователями установите или снимите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="44b8b-118">Для управления архивацией операций обмена данными с внешними пользователями установите или снимите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="44b8b-119">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="44b8b-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="44b8b-120">Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="44b8b-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="44b8b-121">Дополнительные сведения см [Применить политики архивации для пользователей, Скайп для Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="44b8b-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="44b8b-122">Создание новой политики архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44b8b-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="44b8b-123">Новые политики архивации также можно создавать с помощью командлета **New-CsArchivingPolicy** Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44b8b-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="44b8b-124">Для получения дополнительных сведений см раздел справки для командлета [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="44b8b-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="44b8b-125">Порядок создания новой политики архивации на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="44b8b-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="44b8b-126">Данная команда создает новую политику архивации для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="44b8b-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="44b8b-127">Порядок создания новой политики архивации на уровне индивидуальных пользователей</span><span class="sxs-lookup"><span data-stu-id="44b8b-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="44b8b-128">Чтобы создать новую политику архивации на уровне индивидуальных пользователей, просто укажите уникальное удостоверение при создании политики.</span><span class="sxs-lookup"><span data-stu-id="44b8b-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="44b8b-129">Порядок создания новой политики архивации, которая включает архивацию сеансов внутренней связи</span><span class="sxs-lookup"><span data-stu-id="44b8b-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="44b8b-130">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новые политики будут использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="44b8b-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="44b8b-131">Чтобы создать политики, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="44b8b-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="44b8b-132">Например следующая команда создает политики архивации, который разрешает архивацией внутренних сеансы обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="44b8b-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="44b8b-133">Порядок создания новой политики архивации, которая включает архивацию сеансов внутренней и внешней связи</span><span class="sxs-lookup"><span data-stu-id="44b8b-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="44b8b-p104">Несколько значений свойств могут быть изменены путем включения нескольких параметров. Например, данная команда настраивает новую политику для архивации внутренних и внешних сеансов обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="44b8b-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```