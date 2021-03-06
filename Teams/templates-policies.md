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
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507972"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="c337a-103">Создание шаблонов Teams и управление ими в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="c337a-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="c337a-104">Чтобы управлять шаблонами Teams, которые видят пользователи, создайте политики шаблонов в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="c337a-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="c337a-105">В каждой политике шаблонов можно узначить, какие шаблоны должны быть показаны или скрыты.</span><span class="sxs-lookup"><span data-stu-id="c337a-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="c337a-106">Назначайте разным пользователям различные политики шаблонов, чтобы пользователи просматривали только указанные подмножество шаблонов Teams.</span><span class="sxs-lookup"><span data-stu-id="c337a-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="c337a-107">Создание политик шаблонов и назначение доступных шаблонов</span><span class="sxs-lookup"><span data-stu-id="c337a-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="c337a-108">Во sign in to the Teams admin center.</span><span class="sxs-lookup"><span data-stu-id="c337a-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="c337a-109">  >  **Разорите политики шаблонов** Teams.</span><span class="sxs-lookup"><span data-stu-id="c337a-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="c337a-110">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c337a-110">Select **Add**.</span></span>

    ![Выбраны политики шаблонов, выделена надстройка](media/template-policies-1.png)

1. <span data-ttu-id="c337a-112">В разделе **"Параметры политик шаблонов"** заполнять следующие поля:</span><span class="sxs-lookup"><span data-stu-id="c337a-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="c337a-113">Имя политики шаблонов</span><span class="sxs-lookup"><span data-stu-id="c337a-113">Templates Policy name</span></span>

    - <span data-ttu-id="c337a-114">Краткое описание политики шаблонов</span><span class="sxs-lookup"><span data-stu-id="c337a-114">Templates Policy short description</span></span>

2. <span data-ttu-id="c337a-115">В таблице **"Шаблоны для** просмотра" выберите шаблоны, которые нужно скрыть, и выберите **"Скрыть".**</span><span class="sxs-lookup"><span data-stu-id="c337a-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Выбранные шаблоны с выделенной ссылкой "Скрыть"](media/template-policies-2.png)

    <span data-ttu-id="c337a-117">В таблице "Скрытые шаблоны" можно увидеть шаблоны, которые вы **выбрали.**</span><span class="sxs-lookup"><span data-stu-id="c337a-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="c337a-118">Чтобы отрыть скрытые шаблоны, перейдите к таблице **"Скрытые шаблоны".**</span><span class="sxs-lookup"><span data-stu-id="c337a-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="c337a-119">Выберите шаблоны, которые нужно отобрать, и выберите **"Показать".**</span><span class="sxs-lookup"><span data-stu-id="c337a-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Выбранные шаблоны, которые не скрыты](media/template-policies-3.png)

   <span data-ttu-id="c337a-121">Выбранные шаблоны появятся в таблице шаблонов **для** просмотра.</span><span class="sxs-lookup"><span data-stu-id="c337a-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="c337a-122">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="c337a-122">Select **Save**.</span></span>

   <span data-ttu-id="c337a-123">Новая политика шаблонов отобразится в списке **"Политики шаблонов".**</span><span class="sxs-lookup"><span data-stu-id="c337a-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="c337a-124">Назначение пользователей политикам шаблонов</span><span class="sxs-lookup"><span data-stu-id="c337a-124">Assign users to the template policies</span></span>

<span data-ttu-id="c337a-125">Пользователи, которые назначены политике, смогут только просматривать ее шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c337a-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="c337a-126">В **меню "Политики шаблонов"** выберите политику, а затем выберите **"Управление пользователями".**</span><span class="sxs-lookup"><span data-stu-id="c337a-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="c337a-127">Введите пользователей, которые должны назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="c337a-127">Type the users to assign to this policy.</span></span>

   ![назначение пользователей политике шаблонов](media/template-policies-4.png)

3. <span data-ttu-id="c337a-129">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="c337a-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="c337a-130">Для того чтобы новая политика вступила в силу для конечных пользователей, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="c337a-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="c337a-131">Ограничения размера для политик шаблонов</span><span class="sxs-lookup"><span data-stu-id="c337a-131">Size limits for Template policies</span></span>

<span data-ttu-id="c337a-132">В одной политике можно скрыть не более 100 шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c337a-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="c337a-133">Кнопка **"Скрыть"** отключена, если в заданной политике уже скрыто 100 шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c337a-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c337a-134">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="c337a-134">Frequently asked questions</span></span>

<span data-ttu-id="c337a-135">**Вопрос. Можно ли пакетно назначить пользователей политикам шаблонов группы?**</span><span class="sxs-lookup"><span data-stu-id="c337a-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="c337a-136">Ответ. Да, мы поддерживаем пакетное назначение для политики шаблонов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c337a-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="c337a-137">Для этого действия тип политики TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c337a-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="c337a-138">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c337a-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="c337a-139">**Вопрос. Могут ли группы быть назначены политикам шаблонов групп?**</span><span class="sxs-lookup"><span data-stu-id="c337a-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="c337a-140">А. В настоящее время нет.</span><span class="sxs-lookup"><span data-stu-id="c337a-140">A: Currently no.</span></span> <span data-ttu-id="c337a-141">Эта функция будет доступна в будущем.</span><span class="sxs-lookup"><span data-stu-id="c337a-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="c337a-142">**Вопрос. Если будет создан новый шаблон, будет ли он включен в мои политики?**</span><span class="sxs-lookup"><span data-stu-id="c337a-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="c337a-143">О. По умолчанию будут видны все новые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c337a-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="c337a-144">Вы можете скрыть шаблон в Центре администрирования в разделе "Политики шаблонов".</span><span class="sxs-lookup"><span data-stu-id="c337a-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="c337a-145">**Вопрос. Что происходит при удалении шаблона?**</span><span class="sxs-lookup"><span data-stu-id="c337a-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="c337a-146">О. Удаленные шаблоны больше не будут присутствовать в политиках шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c337a-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="c337a-147">**Вопрос. Можно ли назначить нескольким пользователям политику шаблонов в Центре администрирования Teams?**</span><span class="sxs-lookup"><span data-stu-id="c337a-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="c337a-148">Ответ. Да.</span><span class="sxs-lookup"><span data-stu-id="c337a-148">A: Yes.</span></span>

1. <span data-ttu-id="c337a-149">В Центре администрирования перейдите в **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="c337a-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="c337a-150">В таблице списка "Пользователи" выберите пользователей, которые хотите назначить определенной политике шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c337a-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="c337a-151">Выберите "Изменить параметры" и измените поле "Политики шаблонов".</span><span class="sxs-lookup"><span data-stu-id="c337a-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="c337a-152">Выберите "Применить".</span><span class="sxs-lookup"><span data-stu-id="c337a-152">Select apply.</span></span>
   <span data-ttu-id="c337a-153">Узнайте, как назначать политики пользователям в [Microsoft Teams — Microsoft \| Teams, Microsoft Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="c337a-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="c337a-154">**Вопрос. Как просмотреть всех пользователей, которые назначены определенной политике?**</span><span class="sxs-lookup"><span data-stu-id="c337a-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="c337a-155">О. В Центре администрирования:</span><span class="sxs-lookup"><span data-stu-id="c337a-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="c337a-156">Перейдите в **раздел "Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="c337a-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="c337a-157">Выберите фильтр в таблице списка пользователей и фильтрацию политики шаблонов команд.</span><span class="sxs-lookup"><span data-stu-id="c337a-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="c337a-158">Выберите **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="c337a-158">Select **Apply**.</span></span>

![Выбранная политика шаблона и просмотр пользователей](media/template-policies-5.png)

<span data-ttu-id="c337a-160">**Вопрос. Можно ли управлять политиками шаблонов с помощью PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="c337a-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="c337a-161">О. Нет, управление шаблонами в PowerShell не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c337a-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="c337a-162">**Вопрос. Применяются ли политики шаблонов к EDU?**</span><span class="sxs-lookup"><span data-stu-id="c337a-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="c337a-163">О. Нет, политики шаблонов для EDU не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c337a-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c337a-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c337a-164">Related topics</span></span>

- [<span data-ttu-id="c337a-165">Начало работы с шаблонами групп в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="c337a-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="c337a-166">Создание настраиваемой команды</span><span class="sxs-lookup"><span data-stu-id="c337a-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="c337a-167">Создание шаблона из существующей команды</span><span class="sxs-lookup"><span data-stu-id="c337a-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="c337a-168">Создание шаблона команды из существующего шаблона</span><span class="sxs-lookup"><span data-stu-id="c337a-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="c337a-169">Назначение политик пользователям в Microsoft Teams — Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c337a-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="c337a-170">Пакетное назначение пользователей политике</span><span class="sxs-lookup"><span data-stu-id="c337a-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
