---
title: Применение политики архива для пользователей в Skype для бизнеса Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: Сводка. Узнайте, как назначить политику архива пользователям в Skype для бизнеса Server.
ms.openlocfilehash: 1fce0dbd0cc7b0595dcf3cd91baeba9ed364e28a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095493"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="09254-103">Применение политики архива для пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="09254-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="09254-104">**Сводка:** Узнайте, как назначить политику архива пользователям в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="09254-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="09254-105">Если вы создали одну или несколько политик для архива для пользователей, которые имеются в Skype для бизнеса Server, вы можете реализовать поддержку архива для определенных пользователей, применяя соответствующие политики к этим пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="09254-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="09254-106">Например, если вы создаете политику для поддержки архива внутренних коммуникаций, вы можете применить ее по крайней мере к одному пользователю или группе пользователей для поддержки архива сообщений Skype для бизнес-сервера пользователя.</span><span class="sxs-lookup"><span data-stu-id="09254-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09254-107">Если вы включили интеграцию Microsoft Exchange для развертывания, политики Exchange In-Place Hold контролируют, включена ли архивация для пользователей, которые размещены в Exchange, и чтобы их почтовые ящики были In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="09254-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="09254-108">Подробные сведения см. в материале [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) и [Configure integration with Exchange storage for Skype for Business Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="09254-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="09254-109">Применение политики пользователя с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="09254-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="09254-110">Применение политики пользователя с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="09254-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="09254-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="09254-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="09254-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="09254-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="09254-113">В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="09254-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="09254-114">В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="09254-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="09254-115">В **статье Редактирование пользователя Lync Server в** соответствии с политикой архива выберите политику архива, которую необходимо применить. </span><span class="sxs-lookup"><span data-stu-id="09254-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09254-116">Параметры применяют параметры установки **\<Automatic\>** сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="09254-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="09254-117">Данный параметр автоматически применяется сервером.</span><span class="sxs-lookup"><span data-stu-id="09254-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="09254-118">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09254-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="09254-119">Применение политики пользователя с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09254-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="09254-120">Можно также применить политику пользователя с помощью Windows PowerShell **Grant-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="09254-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="09254-121">Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="09254-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="09254-122">Эта команда назначает политику архивизации для каждого пользователя RedmondArchivingPolicy всем пользователям, у которых учетные записи в пуле регистраторов atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="09254-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="09254-123">Сведения о параметре Filter, используемом в этой команде, см. в документации по командлету [Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="09254-123">For details about the Filter parameter used in this command, see the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="09254-124">Следующая команда удаляет любую политику архива для каждого пользователя, ранее назначенную Кену Myer.</span><span class="sxs-lookup"><span data-stu-id="09254-124">The following command removes any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="09254-125">После удаления политики для каждого пользователя управление политикой для каждого пользователя будет автоматически управляться с помощью глобальной политики или, если она существует, его локальной политики сайта.</span><span class="sxs-lookup"><span data-stu-id="09254-125">After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="09254-126">Политика сайта имеет более высокий приоритет, чем глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="09254-126">A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="09254-127">Подробные сведения см. в документации по [cmdlet Grant-CsArchivingPolicy.](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="09254-127">For details, see the [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
