---
title: Управление политиками маршрутинга голосовой почты в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как создавать политики маршрутинга голоса и управлять ими в Microsoft Teams.
ms.openlocfilehash: 00b70363f0034ebc8d99aa59e037658e406af2a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802559"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="36657-103">Управление политиками маршрутинга голосовой почты в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36657-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="36657-104">Если в вашей [](direct-routing-landing-page.md) организации развернута телефонная система прямой маршрутизации, политики маршрутизации голосовой связи позволяют пользователям Teams и Skype для бизнеса Online принимать и звонить на телефонную сеть общего пользования (STN) с использованием локальной инфраструктуры телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="36657-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="36657-105">Политика голосовой маршрутки — это контейнер для записей об использовании ОКП.</span><span class="sxs-lookup"><span data-stu-id="36657-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="36657-106">Вы создаете политики маршрутинга голосовой почты и управляете ими, переходить к политикам маршрутики голосовой почты в Центре администрирования Microsoft Teams или с помощью  >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36657-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="36657-107">Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="36657-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="36657-108">Пользователи будут автоматически получать глобальную политику, если вы не создайте и не назначите ее.</span><span class="sxs-lookup"><span data-stu-id="36657-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="36657-109">Помните, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="36657-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="36657-110">Важно знать, что назначение пользователю политики маршрутинга голосовой почты не позволяет делать звонки по ННР в Teams.</span><span class="sxs-lookup"><span data-stu-id="36657-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="36657-111">Кроме того, необходимо включить прямую маршрутацию телефонной системы и выполнить другие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="36657-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="36657-112">Дополнительные узнать см. [в настройках прямой маршрутинга.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="36657-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="36657-113">Создание настраиваемой политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="36657-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="36657-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36657-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="36657-115">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутации голосовой голосовой почты и нажмите кнопку  >   **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="36657-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="36657-116">![Снимок экрана: страница "Добавление политики маршрутинга голоса" в Центре администрирования Microsoft Teams ](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="36657-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="36657-117">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="36657-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="36657-118">В **области записей об использовании** ДНР щелкните "Добавить использование **ПС** ДНР" и выберите записи, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="36657-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="36657-119">Если вам нужно создать запись использования ННР, нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="36657-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="36657-120">Если вы добавили несколько записей использования ОКП, расположить их в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="36657-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="36657-121">Когда все будет готово, нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="36657-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="36657-122">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="36657-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="36657-123">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="36657-123">Using PowerShell</span></span>

<span data-ttu-id="36657-124">См. [new-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="36657-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="36657-125">Изменение политики голосовой маршрутики</span><span class="sxs-lookup"><span data-stu-id="36657-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="36657-126">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36657-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="36657-127">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="36657-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="36657-128">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам маршрутиации голосовой  >  **голосовой почты.**</span><span class="sxs-lookup"><span data-stu-id="36657-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="36657-129">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="36657-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="36657-130">Нажмите **кнопку "Добавить/удалить** записи использования ННР", внесем нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="36657-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="36657-131">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="36657-131">Using PowerShell</span></span>

<span data-ttu-id="36657-132">См. [set-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="36657-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="36657-133">Назначение пользовательской политики маршрутинга голосовой почты пользователям</span><span class="sxs-lookup"><span data-stu-id="36657-133">Assign a custom voice routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="36657-134">См. также [Grant-CsOnlineVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="36657-134">See also [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="36657-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="36657-135">Related topics</span></span>

[<span data-ttu-id="36657-136">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="36657-136">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="36657-137">Настройка голосовой маршрутии для прямой маршрутинга</span><span class="sxs-lookup"><span data-stu-id="36657-137">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)

[<span data-ttu-id="36657-138">Включение функции "Маршрутизация на основе расположения" для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="36657-138">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)

[<span data-ttu-id="36657-139">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="36657-139">Assign policies to your users in Teams</span></span>](assign-policies.md)
