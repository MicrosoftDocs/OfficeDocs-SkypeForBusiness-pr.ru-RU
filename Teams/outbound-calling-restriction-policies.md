---
title: Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Администраторы могут определять доступные пользователям типы аудиоконференций и вызовов конечных пользователей по ТСОП.
ms.openlocfilehash: b4dbaf73b34da163c731a0514a90b5a3536427fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708825"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="0a770-103">Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="0a770-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="0a770-104">Как администратор, вы можете использовать элементы управления исходящими вызовами для ограничения типов аудиоконференций и вызовов конечных пользователей по ТСОП, доступных пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0a770-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="0a770-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="0a770-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="0a770-107">Управления</span><span class="sxs-lookup"><span data-stu-id="0a770-107">Control</span></span>|<span data-ttu-id="0a770-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0a770-108">Description</span></span>|<span data-ttu-id="0a770-109">Параметры элемента управления</span><span class="sxs-lookup"><span data-stu-id="0a770-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a770-110">Вызовы аудиоконференции по ТСОП</span><span class="sxs-lookup"><span data-stu-id="0a770-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="0a770-111">Ограничивает тип исходящих</span><span class="sxs-lookup"><span data-stu-id="0a770-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="0a770-112">вызовов, которые разрешено выполнять</span><span class="sxs-lookup"><span data-stu-id="0a770-112">calls that are allowed from within</span></span> </br><span data-ttu-id="0a770-113">во время собраний, организованных пользователем.</span><span class="sxs-lookup"><span data-stu-id="0a770-113">meetings organized by a user.</span></span>|<span data-ttu-id="0a770-114">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0a770-114">International and Domestic (default)</span></span></br><span data-ttu-id="0a770-115">Внутренний</span><span class="sxs-lookup"><span data-stu-id="0a770-115">Domestic</span></span></br><span data-ttu-id="0a770-116">Нет</span><span class="sxs-lookup"><span data-stu-id="0a770-116">None</span></span>|
|<span data-ttu-id="0a770-117">Вызовы конечных пользователей по ТСОП</span><span class="sxs-lookup"><span data-stu-id="0a770-117">End user PSTN calls</span></span>|<span data-ttu-id="0a770-118">Ограничивает тип вызовов,</span><span class="sxs-lookup"><span data-stu-id="0a770-118">Restricts the type of calls</span></span> </br><span data-ttu-id="0a770-119">доступных пользователю.</span><span class="sxs-lookup"><span data-stu-id="0a770-119">that can be made by a user.</span></span>|<span data-ttu-id="0a770-120">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0a770-120">International and Domestic (default)</span></span></br><span data-ttu-id="0a770-121">Внутренний</span><span class="sxs-lookup"><span data-stu-id="0a770-121">Domestic</span></span></br><span data-ttu-id="0a770-122">Нет</span><span class="sxs-lookup"><span data-stu-id="0a770-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="0a770-123">Звонок считается внутренним, если номер набирается в той же стране, в которой была настроена программа Office 365 для организатора собрания (в случае голосовой конференции) или конечных пользователей (в случае с ТЕЛЕФОНными звонками для конечных пользователей).</span><span class="sxs-lookup"><span data-stu-id="0a770-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="0a770-124">Ограничение исходящих вызовов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="0a770-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="0a770-125">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0a770-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0a770-126">На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a770-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0a770-127">В верхней части страницы нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="0a770-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="0a770-128">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0a770-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="0a770-129">В разделе **Разрешение на телефонные вызовы во время собраний**выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="0a770-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="0a770-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0a770-130">Click **Save**.</span></span> 

<span data-ttu-id="0a770-131">![Значок с логотипом Skype для бизнеса](media/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="0a770-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="0a770-132">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите в раздел**Пользователи** **голосовой конференции** > и выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0a770-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="0a770-133">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="0a770-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="0a770-134">В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="0a770-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Параметры ограничения исходящих вызовов](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="0a770-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0a770-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="0a770-137">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0a770-137">**Using PowerShell**</span></span>

<span data-ttu-id="0a770-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span><span class="sxs-lookup"><span data-stu-id="0a770-p102">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="0a770-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span><span class="sxs-lookup"><span data-stu-id="0a770-p103">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="0a770-142">В следующей таблице представлена общая информация о каждой политике.</span><span class="sxs-lookup"><span data-stu-id="0a770-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0a770-143">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0a770-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="0a770-144">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь также может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="0a770-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="0a770-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0a770-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="0a770-146">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="0a770-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0a770-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="0a770-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="0a770-148">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера. Этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="0a770-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="0a770-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0a770-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="0a770-150">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0a770-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="0a770-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0a770-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="0a770-152">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="0a770-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0a770-153">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0a770-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="0a770-154">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0a770-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0a770-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0a770-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="0a770-156">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="0a770-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="0a770-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="0a770-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="0a770-158">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0a770-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="0a770-159">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="0a770-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="0a770-160">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="0a770-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
