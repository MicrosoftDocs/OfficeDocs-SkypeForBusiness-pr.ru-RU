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
description: Сведения о том, как использовать политики идентификации вызывающего абонента в Microsoft Teams для изменения или блокировки идентификатора вызывающего абонента для пользователей Teams в Организации.
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255532"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="2f800-103">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f800-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="2f800-104">Администраторы могут использовать политики идентификации вызывающего абонента в Microsoft Teams для изменения или блокировки идентификатора вызывающего абонента (также называемого ИДЕНТИФИКАТОРом вызывающей строки).</span><span class="sxs-lookup"><span data-stu-id="2f800-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="2f800-105">По умолчанию телефонный номер пользователей Teams может отображаться при звонке на телефон PSTN, и телефонный номер абонента PSTN может отображаться при звонках пользователю Teams.</span><span class="sxs-lookup"><span data-stu-id="2f800-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="2f800-106">Вы можете использовать политики идентификации вызывающего абонента, чтобы отобразить дополнительный номер телефона для пользователей Teams в организации или заблокировать входящий номер.</span><span class="sxs-lookup"><span data-stu-id="2f800-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="2f800-107">Например, когда пользователь вызывает звонок, вы можете изменить идентификатор вызывающего абонента, чтобы вместо номера телефона пользователя отображался основной номер телефона Организации.</span><span class="sxs-lookup"><span data-stu-id="2f800-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="2f800-108">Для управления политиками идентификации вызывающего абонента **Voice**  >  в центре администрирования Microsoft Teams можно использовать**политики идентификатора** голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2f800-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2f800-109">Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="2f800-109">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2f800-110">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="2f800-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="2f800-111">Создание политики ИДЕНТИФИКАТОРов для собственного вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="2f800-111">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="2f800-112">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового**  >  **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="2f800-112">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="2f800-113">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2f800-113">Click **Add**.</span></span> <br>
<span data-ttu-id="2f800-114">![Снимок экрана с новой страницей политики идентификации звонящего в центре администрирования](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="2f800-114">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="2f800-115">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="2f800-115">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2f800-116">В этой статье выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="2f800-116">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="2f800-117">**Блокировать входящий вызывающий абонент ID**: Включите этот параметр, чтобы заблокировать отображение идентификатора вызывающего абонента для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="2f800-117">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="2f800-118">**Переопределение политики идентификации вызывающего абонента**: Включите этот параметр, чтобы разрешить пользователям переопределять параметры политики в отношении отображения их номера в callees или нет.</span><span class="sxs-lookup"><span data-stu-id="2f800-118">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="2f800-119">Это означает, что пользователи могут выбрать, нужно ли отображать идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="2f800-119">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="2f800-120">Дополнительные сведения можно найти в разделе [управление конечным пользователем для идентификатора исходящего вызывающего абонента](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="2f800-120">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="2f800-121">**Замените идентификатор вызывающего абонента**: установите для пользователей идентификатор вызывающего абонента, выбирая один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="2f800-121">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="2f800-122">**Номер пользователя**: отображает номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="2f800-122">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="2f800-123">**Номер Услуги**: позволяет указать номер телефона службы, который будет ОТОБРАЖАТЬСЯ как идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="2f800-123">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="2f800-124">**Анонимный**доступ: идентификатор вызывающего абонента отображается как анонимный.</span><span class="sxs-lookup"><span data-stu-id="2f800-124">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="2f800-125">**Замените идентификатор вызывающего абонента на этот номер Услуги**: выберите номер службы, чтобы заменить идентификатор вызывающего абонента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="2f800-125">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="2f800-126">Этот параметр доступен, если вы выбрали **номер службы** в **поле заменить идентификатор вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="2f800-126">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="2f800-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2f800-127">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="2f800-128">Изменение политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="2f800-128">Edit a caller ID policy</span></span>

<span data-ttu-id="2f800-129">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="2f800-129">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="2f800-130">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового**  >  **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="2f800-130">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="2f800-131">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="2f800-131">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2f800-132">Измените нужные параметры и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2f800-132">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="2f800-133">Назначение пользователям политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="2f800-133">Assign a custom caller ID policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="2f800-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2f800-134">Related topics</span></span>

[<span data-ttu-id="2f800-135">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="2f800-135">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[<span data-ttu-id="2f800-136">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="2f800-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
