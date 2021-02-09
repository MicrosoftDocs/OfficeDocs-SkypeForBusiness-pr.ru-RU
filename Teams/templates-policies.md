---
title: Управление шаблонами Teams в Центре администрирования
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Управление шаблонами Teams в Центре администрирования
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9704fdb92689031d44fa692383c701ec47877fc6
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145886"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="10d64-103">Создание шаблонов Teams и управление ими в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="10d64-103">Create and manage Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="10d64-104">Чтобы управлять шаблонами Teams, которые вы показываете пользователям, создайте политики шаблонов в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="10d64-104">Manage the Teams templates that are shown to your end users by creating templates policies in the admin center.</span></span> <span data-ttu-id="10d64-105">В каждой политике шаблонов можно узначить, какие шаблоны должны быть показаны или скрыты.</span><span class="sxs-lookup"><span data-stu-id="10d64-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="10d64-106">Назначайте разным пользователям различные политики шаблонов, чтобы пользователи просматривали только указанные подмножество шаблонов Teams.</span><span class="sxs-lookup"><span data-stu-id="10d64-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="10d64-107">Создание политик шаблонов и назначение доступных шаблонов</span><span class="sxs-lookup"><span data-stu-id="10d64-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="10d64-108">Во sign in to the Teams admin center.</span><span class="sxs-lookup"><span data-stu-id="10d64-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="10d64-109">  >  **Разорите политики шаблонов** Teams.</span><span class="sxs-lookup"><span data-stu-id="10d64-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="10d64-110">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="10d64-110">Select **Add**.</span></span>

    ![Выбраны политики шаблонов, выделена надстройка](media/template-policies-1.png)

1. <span data-ttu-id="10d64-112">В разделе **"Параметры политик шаблонов"** заполнять следующие поля:</span><span class="sxs-lookup"><span data-stu-id="10d64-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="10d64-113">Имя политики шаблонов</span><span class="sxs-lookup"><span data-stu-id="10d64-113">Templates Policy name</span></span>

    - <span data-ttu-id="10d64-114">Краткое описание политики шаблонов</span><span class="sxs-lookup"><span data-stu-id="10d64-114">Templates Policy short description</span></span>

2. <span data-ttu-id="10d64-115">В таблице **"Шаблоны для** просмотра" выберите шаблоны, которые нужно скрыть, и выберите **"Скрыть".**</span><span class="sxs-lookup"><span data-stu-id="10d64-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Выбранные шаблоны с выделенной ссылкой "Скрыть"](media/template-policies-2.png)

    <span data-ttu-id="10d64-117">В таблице "Скрытые шаблоны" можно увидеть шаблоны, которые вы **выбрали.**</span><span class="sxs-lookup"><span data-stu-id="10d64-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="10d64-118">Чтобы отрыть скрытые шаблоны, перейдите к таблице **"Скрытые шаблоны".**</span><span class="sxs-lookup"><span data-stu-id="10d64-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="10d64-119">Выберите шаблоны, которые нужно отобрать, и выберите **"Показать".**</span><span class="sxs-lookup"><span data-stu-id="10d64-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Выбранные шаблоны с выделенной ссылкой "Скрыть"](media/template-policies-3.png)

   <span data-ttu-id="10d64-121">Выбранные шаблоны появятся в таблице шаблонов **для** просмотра.</span><span class="sxs-lookup"><span data-stu-id="10d64-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="10d64-122">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="10d64-122">Select **Save**.</span></span>

   <span data-ttu-id="10d64-123">Новая политика шаблонов отобразится в списке **"Политики шаблонов".**</span><span class="sxs-lookup"><span data-stu-id="10d64-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="10d64-124">Назначение пользователей политикам шаблонов</span><span class="sxs-lookup"><span data-stu-id="10d64-124">Assign users to the template policies</span></span>

<span data-ttu-id="10d64-125">Пользователи, которые назначены политике, смогут только просматривать ее шаблоны.</span><span class="sxs-lookup"><span data-stu-id="10d64-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="10d64-126">В **меню "Политики шаблонов"** выберите политику, а затем выберите **"Управление пользователями".**</span><span class="sxs-lookup"><span data-stu-id="10d64-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="10d64-127">Введите пользователей, которые должны назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="10d64-127">Type the users to assign to this policy.</span></span>

   ![Выбранные шаблоны с выделенной ссылкой "Скрыть"](media/template-policies-4.png)

3. <span data-ttu-id="10d64-129">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="10d64-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="10d64-130">Для того чтобы новая политика вступила в силу для конечных пользователей, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="10d64-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="10d64-131">Ограничения размера для политик шаблонов</span><span class="sxs-lookup"><span data-stu-id="10d64-131">Size limits for Template policies</span></span>

<span data-ttu-id="10d64-132">В одной политике можно скрыть не более 100 шаблонов.</span><span class="sxs-lookup"><span data-stu-id="10d64-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="10d64-133">Кнопка **"Скрыть"** отключена, если в заданной политике уже скрыто 100 шаблонов.</span><span class="sxs-lookup"><span data-stu-id="10d64-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="10d64-134">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="10d64-134">Frequently asked questions</span></span>

<span data-ttu-id="10d64-135">**Вопрос. Можно ли пакетно назначить пользователей политикам шаблонов группы?**</span><span class="sxs-lookup"><span data-stu-id="10d64-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="10d64-136">Ответ. Да, мы поддерживаем пакетное назначение для политики шаблонов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10d64-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="10d64-137">Для этого действия тип политики TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="10d64-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="10d64-138">Подробнее</span><span class="sxs-lookup"><span data-stu-id="10d64-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="10d64-139">**Вопрос. Могут ли группы быть назначены политикам шаблонов групп?**</span><span class="sxs-lookup"><span data-stu-id="10d64-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="10d64-140">А. В настоящее время нет.</span><span class="sxs-lookup"><span data-stu-id="10d64-140">A: Currently no.</span></span> <span data-ttu-id="10d64-141">Эта функция будет доступна в будущем.</span><span class="sxs-lookup"><span data-stu-id="10d64-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="10d64-142">**Вопрос. Если будет создан новый шаблон, будет ли он включен в мои политики?**</span><span class="sxs-lookup"><span data-stu-id="10d64-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="10d64-143">О. По умолчанию будут видны все новые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="10d64-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="10d64-144">Вы можете скрыть шаблон в Центре администрирования в разделе "Политики шаблонов".</span><span class="sxs-lookup"><span data-stu-id="10d64-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="10d64-145">**Вопрос. Что происходит при удалении шаблона?**</span><span class="sxs-lookup"><span data-stu-id="10d64-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="10d64-146">О. Все удаленные шаблоны больше не будут присутствовать в политиках шаблонов.</span><span class="sxs-lookup"><span data-stu-id="10d64-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="10d64-147">**Вопрос. Можно ли назначить нескольким пользователям политику шаблонов в Центре администрирования Teams?**</span><span class="sxs-lookup"><span data-stu-id="10d64-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="10d64-148">Ответ. Да.</span><span class="sxs-lookup"><span data-stu-id="10d64-148">A: Yes.</span></span>

1. <span data-ttu-id="10d64-149">В Центре администрирования перейдите в **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="10d64-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="10d64-150">В таблице списка "Пользователи" выберите пользователей, которые хотите назначить определенной политике шаблонов.</span><span class="sxs-lookup"><span data-stu-id="10d64-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="10d64-151">Выберите "Изменить параметры" и измените поле "Политики шаблонов".</span><span class="sxs-lookup"><span data-stu-id="10d64-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="10d64-152">Выберите "Применить".</span><span class="sxs-lookup"><span data-stu-id="10d64-152">Select apply.</span></span>
   <span data-ttu-id="10d64-153">Подробнее о назначении политик пользователям [в Microsoft Teams — Microsoft Teams в Microsoft \| Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="10d64-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="10d64-154">**Вопрос. Как просмотреть всех пользователей, которые назначены определенной политике?**</span><span class="sxs-lookup"><span data-stu-id="10d64-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="10d64-155">А. В Центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="10d64-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="10d64-156">Перейдите в **раздел "Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="10d64-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="10d64-157">Выберите фильтр в таблице списка пользователей и фильтрацию политики шаблонов команд.</span><span class="sxs-lookup"><span data-stu-id="10d64-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="10d64-158">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="10d64-158">Select **Apply**.</span></span>

![Выбранные шаблоны с выделенной ссылкой "Скрыть"](media/template-policies-5.png)

<span data-ttu-id="10d64-160">**Вопрос. Можно ли управлять политиками шаблонов с помощью PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="10d64-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="10d64-161">О. Нет, эта поддержка не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="10d64-161">A: No, this isn't supported.</span></span>

<span data-ttu-id="10d64-162">**Вопрос. Применяются ли политики шаблонов к EDU?**</span><span class="sxs-lookup"><span data-stu-id="10d64-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="10d64-163">О. Нет, эта поддержка не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="10d64-163">A: No, this isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10d64-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="10d64-164">Related topics</span></span>

- [<span data-ttu-id="10d64-165">Начало работы с шаблонами групп в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="10d64-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="10d64-166">Создание настраиваемой команды</span><span class="sxs-lookup"><span data-stu-id="10d64-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="10d64-167">Создание шаблона из существующей команды</span><span class="sxs-lookup"><span data-stu-id="10d64-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="10d64-168">Создание шаблона команды из существующего шаблона</span><span class="sxs-lookup"><span data-stu-id="10d64-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="10d64-169">Назначение политик пользователям в Microsoft Teams — Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="10d64-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="10d64-170">Пакетное назначение пользователей политике</span><span class="sxs-lookup"><span data-stu-id="10d64-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
