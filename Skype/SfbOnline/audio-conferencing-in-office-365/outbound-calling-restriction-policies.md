---
title: Политики ограничения исходящих вызовов аудиоконференций и вызовов пользователей по ТСОП
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут определять доступные пользователям типы аудиоконференций и вызовов конечных пользователей по ТСОП.
ms.openlocfilehash: fd1a3b770debfcc6aa048d150b6536c94db4f9ce
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856884"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="870d9-103">Политики ограничения исходящих вызовов аудиоконференций и вызовов пользователей по ТСОП</span><span class="sxs-lookup"><span data-stu-id="870d9-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="870d9-104">Как администратор, вы можете использовать элементы управления исходящими вызовами для ограничения типов аудиоконференций и вызовов конечных пользователей по ТСОП, доступных пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="870d9-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="870d9-105">Элементы управления исходящими вызовами можно использовать отдельно для каждого пользователя. Они состоят из следующих двух элементов управления, каждый из которых ограничивает определенный тип исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="870d9-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="870d9-106">По умолчанию оба элемента управления разрешают международные и внутренние исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="870d9-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="870d9-107">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="870d9-107">CONTROL</span></span>|<span data-ttu-id="870d9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="870d9-108">Description</span></span>|<span data-ttu-id="870d9-109">Параметры элемента управления</span><span class="sxs-lookup"><span data-stu-id="870d9-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="870d9-110">Вызовы аудиоконференции по ТСОП</span><span class="sxs-lookup"><span data-stu-id="870d9-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="870d9-111">Ограничивает тип исходящих</span><span class="sxs-lookup"><span data-stu-id="870d9-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="870d9-112">вызовов, которые разрешено выполнять</span><span class="sxs-lookup"><span data-stu-id="870d9-112">calls that are allowed from within</span></span> </br><span data-ttu-id="870d9-113">во время собраний, организованных пользователем.</span><span class="sxs-lookup"><span data-stu-id="870d9-113">meetings organized by a user.</span></span>|<span data-ttu-id="870d9-114">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="870d9-114">International and Domestic (default)</span></span></br><span data-ttu-id="870d9-115">Внутренние</span><span class="sxs-lookup"><span data-stu-id="870d9-115">Domestic</span></span></br><span data-ttu-id="870d9-116">Нет</span><span class="sxs-lookup"><span data-stu-id="870d9-116">None</span></span>|
|<span data-ttu-id="870d9-117">Вызовы конечных пользователей по ТСОП</span><span class="sxs-lookup"><span data-stu-id="870d9-117">End user PSTN calls</span></span>|<span data-ttu-id="870d9-118">Ограничивает тип вызовов,</span><span class="sxs-lookup"><span data-stu-id="870d9-118">Restricts the type of calls</span></span> </br><span data-ttu-id="870d9-119">доступных пользователю.</span><span class="sxs-lookup"><span data-stu-id="870d9-119">that can be made by a user.</span></span>|<span data-ttu-id="870d9-120">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="870d9-120">International and Domestic (default)</span></span></br><span data-ttu-id="870d9-121">Внутренние</span><span class="sxs-lookup"><span data-stu-id="870d9-121">Domestic</span></span></br><span data-ttu-id="870d9-122">Нет</span><span class="sxs-lookup"><span data-stu-id="870d9-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="870d9-123">Вызов считается внутренним, если вызываемый номер телефона находится в стране, указанной в Office 365 организатора собрания (в случае аудиоконференций) или конечного пользователя (в случае вызовов конечного пользователя по ТСОП).</span><span class="sxs-lookup"><span data-stu-id="870d9-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="870d9-124">Ограничение исходящих вызовов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="870d9-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="870d9-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="870d9-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="870d9-126">На панели навигации слева нажмите **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="870d9-126">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="870d9-127">В верхней части страницы нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="870d9-127">At the top of the page, choose **Users**.</span></span>

3. <span data-ttu-id="870d9-128">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="870d9-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="870d9-129">В разделе **Разрешение на телефонные вызовы во время собраний**выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="870d9-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="870d9-130">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="870d9-130">Click **Save**.</span></span> 

<span data-ttu-id="870d9-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="870d9-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1.  <span data-ttu-id="870d9-132">В **Центре администрирования Skype для бизнеса** на панели навигации слева перейдите в раздел **Аудиоконференции** > **Пользователи**, затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="870d9-132">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Dial-in users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="870d9-133">На панели действий нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="870d9-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="870d9-134">В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="870d9-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Параметры ограничения исходящих вызовов](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="870d9-136">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="870d9-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="870d9-137">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="870d9-137">**Using PowerShell**</span></span>

<span data-ttu-id="870d9-138">Ограничения исходящих вызовов регулируются единой политикой под названием OnlineDialOutPolicy, в которой для каждого типа вызовов предусмотрен атрибут ограничения.</span><span class="sxs-lookup"><span data-stu-id="870d9-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="870d9-139">Эту политику нельзя изменить в соответствии с потребностями пользователя, но можно использовать предварительно заданные экземпляры политики для каждого сочетания параметров.</span><span class="sxs-lookup"><span data-stu-id="870d9-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="870d9-140">Вы можете использовать командлет Get-CSOnlineDialOutPolicy для просмотра политик в отношении исходящих вызовов, и командлет Grant-CSDialOutPolicy — для закрепления их за пользователями</span><span class="sxs-lookup"><span data-stu-id="870d9-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="870d9-141">(обратите внимание, что командлет Grant не содержит слово «Online», в отличие от командлета Get).</span><span class="sxs-lookup"><span data-stu-id="870d9-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="870d9-142">В следующей таблице представлена общая информация о каждой политике.</span><span class="sxs-lookup"><span data-stu-id="870d9-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="870d9-143">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="870d9-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="870d9-144">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь также может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="870d9-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="870d9-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="870d9-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="870d9-146">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="870d9-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="870d9-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="870d9-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="870d9-148">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера. Этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="870d9-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="870d9-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="870d9-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="870d9-150">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="870d9-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="870d9-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="870d9-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="870d9-152">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="870d9-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="870d9-153">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="870d9-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="870d9-154">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="870d9-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="870d9-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="870d9-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="870d9-156">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="870d9-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="870d9-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="870d9-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="870d9-158">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="870d9-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="870d9-159">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="870d9-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="870d9-160">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="870d9-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
