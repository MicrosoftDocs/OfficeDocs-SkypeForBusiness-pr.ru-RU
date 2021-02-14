---
title: Политика архивирования
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 'Политики архива используются для того, чтобы включить и отключить архивировать для пользователей, которые были в Skype для бизнеса Server. В каждой политике архивирования можно включить или отключить архивирование для следующих параметров:'
ms.openlocfilehash: 19bc0612208e719b7a963bf4c7f0dc6a9cc69537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826949"
---
# <a name="archiving-policy"></a><span data-ttu-id="6b47d-104">Политика архивирования</span><span class="sxs-lookup"><span data-stu-id="6b47d-104">Archiving Policy</span></span>
 
<span data-ttu-id="6b47d-105">Политики архива используются для того, чтобы включить и отключить архивировать для пользователей, которые были в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6b47d-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="6b47d-106">В каждой политике архивирования можно включить или отключить архивирование для следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="6b47d-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="6b47d-107">Внутренняя связь</span><span class="sxs-lookup"><span data-stu-id="6b47d-107">Internal communications</span></span>
    
- <span data-ttu-id="6b47d-108">Внешняя связь (взаимодействие, в котором принимает участие хотя бы один пользователь, расположенный за пределами вашей внутренней сети)</span><span class="sxs-lookup"><span data-stu-id="6b47d-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="6b47d-109">Политики архивирования включают глобальную политику и, дополнительно, одну или несколько политик сайтов и пользователей:</span><span class="sxs-lookup"><span data-stu-id="6b47d-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="6b47d-110">**Глобальная политика** Глобальная политика создается по умолчанию во всех развертываниях.</span><span class="sxs-lookup"><span data-stu-id="6b47d-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="6b47d-111">Глобальную политику можно отредактировать, но удалить эту политику архивирования невозможно.</span><span class="sxs-lookup"><span data-stu-id="6b47d-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="6b47d-112">Если попытаться удалить ее, все параметры сбрасываются до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b47d-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="6b47d-113">**Политика сайта (необязательно)** Можно указать одну или несколько политик архива сайта, каждая из которых может быть настроена для того, чтобы включить или отключить архивировать внутреннюю или внешнюю связь для одного сайта.</span><span class="sxs-lookup"><span data-stu-id="6b47d-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="6b47d-114">Политика сайта переопределяет глобальную политику, но только для тех сайтов, которые указаны в политиках архивирования сайтов.</span><span class="sxs-lookup"><span data-stu-id="6b47d-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="6b47d-115">Политики сайта можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="6b47d-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="6b47d-116">**Политика пользователя (необязательно)** Можно указать одну или несколько политик архива пользователя, каждая из которых может быть настроена для того, чтобы включить или отключить архивировать внутреннюю или внешнюю связь для определенного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="6b47d-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="6b47d-117">Политика пользователя переопределяет глобальную политику и политики сайтов, но только для тех пользователей и групп пользователей, которым назначены политики архивирования на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="6b47d-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="6b47d-118">Политики пользователей можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="6b47d-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6b47d-119">Политики архива применяются только к пользователям Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6b47d-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="6b47d-120">Если для хранения архивных данных в Microsoft Exchange используется интеграция Exchange, политики Exchange 2013 контролируют архивацию для пользователей, которые хранятся в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="6b47d-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="6b47d-121">Чтобы включить архив для этих пользователей, почтовый ящик пользователя должен быть помещен на In-Place удержания.</span><span class="sxs-lookup"><span data-stu-id="6b47d-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="6b47d-p107">На странице **Политика архивирования** перечислены все политики архивирования, которые настроены для развертывания. Здесь также показано имя политики, область действия (глобальная, сайта или пользователя) и то, какие параметры архивирования включены для политики архивирования. На странице **Политика архивирования** предоставлены следующие варианты действий:</span><span class="sxs-lookup"><span data-stu-id="6b47d-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="6b47d-125">**Новый** Вы можете добавить одну или несколько из следующих дополнительных политик архива:</span><span class="sxs-lookup"><span data-stu-id="6b47d-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="6b47d-126">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="6b47d-126">Site policy</span></span>
    
  - <span data-ttu-id="6b47d-127">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="6b47d-127">User policy</span></span>
    
- <span data-ttu-id="6b47d-128">**Правка** Вы можете изменить параметры любой из политик архива, перечисленных на странице.</span><span class="sxs-lookup"><span data-stu-id="6b47d-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="6b47d-129">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="6b47d-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="6b47d-130">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры архивирования для политики архивирования.</span><span class="sxs-lookup"><span data-stu-id="6b47d-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="6b47d-131">**Выбрать все** Этот параметр выбирает все политики архивирования в списке.</span><span class="sxs-lookup"><span data-stu-id="6b47d-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="6b47d-132">**Удалить** Этот параметр удаляет все выбранные политики архивирования.</span><span class="sxs-lookup"><span data-stu-id="6b47d-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="6b47d-133">**Действие** С помощью этого параметра можно быстро включить или отключить архивировать внутренние или внешние коммуникации в любой политике, которая указана на странице, а не изменять политику.</span><span class="sxs-lookup"><span data-stu-id="6b47d-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="6b47d-134">Параметры, доступные в разделе **Действие**, зависят от того, какой параметр выбран в текущий момент в политике архивирования.</span><span class="sxs-lookup"><span data-stu-id="6b47d-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="6b47d-135">Доступны все параметры, кроме тех, которые включены в политике архивирования в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="6b47d-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="6b47d-136">Параметры включают следующие:</span><span class="sxs-lookup"><span data-stu-id="6b47d-136">Options include the following:</span></span>
    
  - <span data-ttu-id="6b47d-137">**Включить архивирование внутренней связи**</span><span class="sxs-lookup"><span data-stu-id="6b47d-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="6b47d-138">**Отключить архивирование внутренней связи**</span><span class="sxs-lookup"><span data-stu-id="6b47d-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="6b47d-139">**Включить архивирование внешней связи**</span><span class="sxs-lookup"><span data-stu-id="6b47d-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="6b47d-140">**Отключить архивирование внешней связи**</span><span class="sxs-lookup"><span data-stu-id="6b47d-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="6b47d-141">**Обновление** Можно обновить **страницу политики архива,** чтобы проверить состояние параметров всех политик архива.</span><span class="sxs-lookup"><span data-stu-id="6b47d-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="6b47d-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="6b47d-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

