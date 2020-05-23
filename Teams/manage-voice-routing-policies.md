---
title: Управление политиками голосовой маршрутизации в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как создавать политики голосовой маршрутизации и управлять ими в Microsoft Teams.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350193"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="16277-103">Управление политиками голосовой маршрутизации в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16277-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="16277-104">Если вы развернули [прямую маршрутизацию телефонной системы](direct-routing-landing-page.md) в своей организации, вы используете политики голосовой связи, позволяющие пользователям групп и Skype для бизнеса Online получать и звонить по телефонной сети общего пользования (PSTN) с помощью локальной инфраструктуры телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="16277-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="16277-105">Политика маршрутизации голосовой связи — это контейнер для записей об использовании КТСОП.</span><span class="sxs-lookup"><span data-stu-id="16277-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="16277-106">Вы можете создавать политики голосовой маршрутизации и управлять ими, переключаясь **на**  >  **политики маршрутизации голосовой голосовой связи** в центре администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16277-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="16277-107">Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="16277-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="16277-108">Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="16277-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="16277-109">Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.</span><span class="sxs-lookup"><span data-stu-id="16277-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="16277-110">Важно знать, что назначение пользователю политики голосовой маршрутизации не позволяет им звонить по PSTN в Teams.</span><span class="sxs-lookup"><span data-stu-id="16277-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="16277-111">Кроме того, вам необходимо включить прямую маршрутизацию на телефонную систему и выполнить другие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="16277-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="16277-112">Дополнительные сведения можно найти в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="16277-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="16277-113">Создание настраиваемой политики голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="16277-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16277-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16277-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="16277-115">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Voice**  >  **политики маршрутизации голосовой голосовой связи**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="16277-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="16277-116">![Снимок экрана: страница "Добавление политики голосовой маршрутизации" в центре администрирования Microsoft Teams](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="16277-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="16277-117">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="16277-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="16277-118">В разделе **записи использования PSTN**щелкните **Добавить использование КТСОП**и выберите записи, которые вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="16277-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="16277-119">Если вам нужно создать новую запись использования КТСОП, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="16277-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="16277-120">Если вы добавили несколько записей PSTN Usage, расположите их в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="16277-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="16277-121">Когда все будет готово, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="16277-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="16277-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16277-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16277-123">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="16277-123">Using PowerShell</span></span>

<span data-ttu-id="16277-124">Просмотреть раздел [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="16277-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="16277-125">Изменение политики голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="16277-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16277-126">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16277-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="16277-127">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="16277-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="16277-128">В левой области навигации центра администрирования Microsoft Teams **перейдите на вкладку**  >  **политики маршрутизации голосовой голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="16277-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="16277-129">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="16277-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="16277-130">Нажмите кнопку **Добавить/удалить записи использования PSTN**, внесите необходимые изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16277-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16277-131">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="16277-131">Using PowerShell</span></span>

<span data-ttu-id="16277-132">Смотрите раздел [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="16277-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="16277-133">Назначение настраиваемой политики голосовой маршрутизации пользователям</span><span class="sxs-lookup"><span data-stu-id="16277-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="16277-134">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16277-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="16277-135">Чтобы назначить политику для одного пользователя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="16277-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="16277-136">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="16277-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="16277-137">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="16277-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="16277-138">В разделе **Политика маршрутизации голосовой связи**выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16277-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="16277-139">Чтобы назначить политику нескольким пользователям за один раз, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="16277-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="16277-140">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**, а затем найдите пользователей или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="16277-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="16277-141">В столбце **&#x2713;** (флажок) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="16277-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="16277-142">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочка) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="16277-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="16277-143">Нажмите кнопку **изменить параметры**, внесите необходимые изменения и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="16277-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="16277-144">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="16277-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="16277-145">В левой области навигации центра администрирования Microsoft Teams **перейдите на вкладку**  >  **политики маршрутизации голосовой голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="16277-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="16277-146">Выберите политику, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="16277-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="16277-147">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="16277-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="16277-148">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="16277-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="16277-149">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="16277-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="16277-150">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16277-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="16277-151">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="16277-151">Using PowerShell</span></span>

<span data-ttu-id="16277-152">Просмотр [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="16277-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="16277-153">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="16277-153">Related topics</span></span>

- [<span data-ttu-id="16277-154">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="16277-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="16277-155">Настройка маршрутизации голосовой связи для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="16277-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="16277-156">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="16277-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="16277-157">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="16277-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
