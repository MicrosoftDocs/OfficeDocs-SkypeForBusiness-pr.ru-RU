---
title: Управление политиками идентификации вызывающего абонента в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики ИД звоня в Microsoft Teams и управлять ими, чтобы изменить или заблокировать ИД вызываемого пользователя Teams в вашей организации.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102785"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="b4781-103">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4781-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="b4781-104">Администраторы могут использовать политики ИД звоня в Microsoft Teams, чтобы изменить или заблокировать его (также известный как ИД строки звонков).</span><span class="sxs-lookup"><span data-stu-id="b4781-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="b4781-105">По умолчанию телефонный номер пользователей Teams можно увидеть при звонии на телефон по ПСОП, а номер телефона вызывающих пользователей ДНР можно увидеть, когда звонят пользователи Teams.</span><span class="sxs-lookup"><span data-stu-id="b4781-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="b4781-106">С помощью политик ИД звоня можно отобразить альтернативный номер телефона для пользователей Teams в организации или заблокировать отображение входящих номеров.</span><span class="sxs-lookup"><span data-stu-id="b4781-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="b4781-107">Например, когда звонят пользователи, вы можете изменить их ИД так, чтобы вместо номеров пользователей отображался основной номер телефона вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b4781-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="b4781-108">Вы управляете политиками по учетным данным вызываемого звоня, переходить к политикам ИД вызываемого звоня в Центре администрирования   >   Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b4781-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b4781-109">Вы можете использовать глобальную (по умолчанию в пределах организации) политику или создавать и присваивать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="b4781-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="b4781-110">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="b4781-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="b4781-111">Создание настраиваемой политики ИД вызываемого вызова</span><span class="sxs-lookup"><span data-stu-id="b4781-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="b4781-112">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам распознавания голосовых  >  **вызовов.**</span><span class="sxs-lookup"><span data-stu-id="b4781-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="b4781-113">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b4781-113">Click **Add**.</span></span> <br>
<span data-ttu-id="b4781-114">![Снимок экрана: страница политики "Новый адрес" в Центре администрирования](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="b4781-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="b4781-115">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="b4781-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b4781-116">В этом окте выберите нужные параметры:</span><span class="sxs-lookup"><span data-stu-id="b4781-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="b4781-117">**Блокировать ИД входящих звонков:** включив этот параметр, вы не можете отобразить Входящие звонки, включив этот параметр.</span><span class="sxs-lookup"><span data-stu-id="b4781-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="b4781-118">**Переопределение** политики "ИД вызываемого пользователя": включив этот параметр, пользователи смогут переопределять параметры политики, касающиеся отображения номера вызываемого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4781-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="b4781-119">Это означает, что пользователи могут выбрать, следует ли отображать свой ИД звоня.</span><span class="sxs-lookup"><span data-stu-id="b4781-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="b4781-120">Дополнительные сведения см. в [подконтрольной пользователю](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)области управления исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="b4781-120">For more information, see [End user control of outbound caller ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="b4781-121">**Замените ИД вызываемого** пользователя следующим образом: установите для пользователей этот ИД:</span><span class="sxs-lookup"><span data-stu-id="b4781-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="b4781-122">**Номер пользователя:** отображает номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4781-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="b4781-123">**Номер службы:** позволяет настроить номер телефона службы, который будет отображаться в качестве ИД вызываемого.</span><span class="sxs-lookup"><span data-stu-id="b4781-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="b4781-124">**Anonymous**: Displays the caller ID as Anonymous.</span><span class="sxs-lookup"><span data-stu-id="b4781-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="b4781-125">**Замените ИД вызываемого** вызываемого пользователя на номер службы: выберите номер службы, который заменит ИД вызываемого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4781-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="b4781-126">Этот параметр доступен, если  вы выбрали "Номер службы" в оке **"Заменить ИД вызываемого звонка".**</span><span class="sxs-lookup"><span data-stu-id="b4781-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="b4781-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b4781-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="b4781-128">Изменение политики ИД вызываемого вызова</span><span class="sxs-lookup"><span data-stu-id="b4781-128">Edit a caller ID policy</span></span>

<span data-ttu-id="b4781-129">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="b4781-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="b4781-130">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам распознавания голосовых  >  **вызовов.**</span><span class="sxs-lookup"><span data-stu-id="b4781-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="b4781-131">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b4781-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b4781-132">Измените нужные параметры и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="b4781-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="b4781-133">Назначение пользователям настраиваемой политики ИД вызываемого пользователя</span><span class="sxs-lookup"><span data-stu-id="b4781-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="b4781-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b4781-134">Related topics</span></span>

[<span data-ttu-id="b4781-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="b4781-135">New-CsCallingLineIdentity</span></span>](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="b4781-136">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="b4781-136">Assign policies to your users in Teams</span></span>](assign-policies.md)