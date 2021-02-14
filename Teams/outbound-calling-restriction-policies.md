---
title: Ограничения на исходящие звонки — аудиоконференция для & звонков по ННР
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Администраторы могут определять доступные пользователям типы аудиоконференций и вызовов конечных пользователей по ТСОП.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908658"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="1f0af-103">Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="1f0af-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="1f0af-104">Как администратор, вы можете использовать элементы управления исходящими вызовами для ограничения типов аудиоконференций и вызовов конечных пользователей по ТСОП, доступных пользователям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1f0af-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="1f0af-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span><span class="sxs-lookup"><span data-stu-id="1f0af-p101">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="1f0af-107">Управление</span><span class="sxs-lookup"><span data-stu-id="1f0af-107">Control</span></span>|<span data-ttu-id="1f0af-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1f0af-108">Description</span></span>|<span data-ttu-id="1f0af-109">Параметры элемента управления</span><span class="sxs-lookup"><span data-stu-id="1f0af-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f0af-110">Вызовы аудиоконференции по ТСОП</span><span class="sxs-lookup"><span data-stu-id="1f0af-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="1f0af-111">Ограничивает тип исходящих</span><span class="sxs-lookup"><span data-stu-id="1f0af-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="1f0af-112">вызовов, которые разрешено выполнять</span><span class="sxs-lookup"><span data-stu-id="1f0af-112">calls that are allowed from within</span></span> </br><span data-ttu-id="1f0af-113">во время собраний, организованных пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f0af-113">meetings organized by a user.</span></span>|<span data-ttu-id="1f0af-114">Любое назначение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1f0af-114">Any destination (default)</span></span></br><span data-ttu-id="1f0af-115">В той же стране или регионе, что и организатор</span><span class="sxs-lookup"><span data-stu-id="1f0af-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="1f0af-116">[Только страны или регионы зоны А](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="1f0af-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="1f0af-117">Не разрешайте</span><span class="sxs-lookup"><span data-stu-id="1f0af-117">Don't allow</span></span>|
|<span data-ttu-id="1f0af-118">Вызовы конечных пользователей по ТСОП</span><span class="sxs-lookup"><span data-stu-id="1f0af-118">End user PSTN calls</span></span>|<span data-ttu-id="1f0af-119">Ограничивает тип вызовов,</span><span class="sxs-lookup"><span data-stu-id="1f0af-119">Restricts the type of calls</span></span> </br><span data-ttu-id="1f0af-120">доступных пользователю.</span><span class="sxs-lookup"><span data-stu-id="1f0af-120">that can be made by a user.</span></span>|<span data-ttu-id="1f0af-121">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1f0af-121">International and Domestic (default)</span></span></br><span data-ttu-id="1f0af-122">Внутренний</span><span class="sxs-lookup"><span data-stu-id="1f0af-122">Domestic</span></span></br><span data-ttu-id="1f0af-123">Нет</span><span class="sxs-lookup"><span data-stu-id="1f0af-123">None</span></span>|

<span data-ttu-id="1f0af-124">Чтобы узнать, какие страны и регионы считаются зонами А, см. зоны стран и регионов для [аудиоконференции.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="1f0af-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1f0af-125">Звонок считается внутренним, если набраный номер находится в той же стране, где настроена система Microsoft 365 или Office 365 для организатора собрания (в случае аудиоконференции), или для конечного пользователя (в случае звонков по ННР).</span><span class="sxs-lookup"><span data-stu-id="1f0af-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="1f0af-126">Ограничение исходящих вызовов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="1f0af-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="1f0af-127">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="1f0af-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1f0af-128">В области навигации слева выберите "Пользователи" и щелкните отображаемую имя пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f0af-128">In the left navigation, click **Users**, and then click the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="1f0af-129">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1f0af-129">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="1f0af-130">В **диалоговом окте "Телефонное** с выходом из собраний" выберите нужный вариант ограничения на ветвь.</span><span class="sxs-lookup"><span data-stu-id="1f0af-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="1f0af-131">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1f0af-131">Click **Save**.</span></span> 

<span data-ttu-id="1f0af-132">![Значок с логотипом Skype для бизнеса](media/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="1f0af-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1f0af-133">В Центре **администрирования Skype** для бизнеса на левой навигации перейдите в список пользователей аудиоконференции, а затем выберите пользователя в списке  >  доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f0af-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="1f0af-134">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="1f0af-134">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="1f0af-135">В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="1f0af-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Параметры ограничения исходящих вызовов](media/restrictions-to-dial-outs.png)
      

4. <span data-ttu-id="1f0af-137">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1f0af-137">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="1f0af-138">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1f0af-138">**Using PowerShell**</span></span>

<span data-ttu-id="1f0af-139">Ограничения исходящих вызовов регулируются единой политикой под названием OnlineDialOutPolicy, в которой для каждого типа вызовов предусмотрен атрибут ограничения.</span><span class="sxs-lookup"><span data-stu-id="1f0af-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="1f0af-140">Эту политику нельзя изменить в соответствии с потребностями пользователя, но можно использовать предварительно заданные экземпляры политики для каждого сочетания параметров.</span><span class="sxs-lookup"><span data-stu-id="1f0af-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="1f0af-141">Вы можете использовать командлет Get-CSOnlineDialOutPolicy для просмотра политик в отношении исходящих вызовов, и командлет Grant-CSDialOutPolicy — для закрепления их за пользователями</span><span class="sxs-lookup"><span data-stu-id="1f0af-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="1f0af-142">(Обратите внимание, что для этого не требуется слово "В сети".)</span><span class="sxs-lookup"><span data-stu-id="1f0af-142">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="1f0af-143">В следующей таблице представлена общая информация о каждой политике.</span><span class="sxs-lookup"><span data-stu-id="1f0af-143">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1f0af-144">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="1f0af-144">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="1f0af-145">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь также может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="1f0af-145">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="1f0af-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="1f0af-146">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="1f0af-147">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="1f0af-147">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="1f0af-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="1f0af-148">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="1f0af-149">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера. Этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="1f0af-149">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="1f0af-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="1f0af-150">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="1f0af-151">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1f0af-151">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="1f0af-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="1f0af-152">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="1f0af-153">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="1f0af-153">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="1f0af-154">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="1f0af-154">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="1f0af-155">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1f0af-155">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="1f0af-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="1f0af-156">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="1f0af-157">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="1f0af-157">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="1f0af-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="1f0af-158">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="1f0af-159">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1f0af-159">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="1f0af-160">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="1f0af-160">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="1f0af-161">Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="1f0af-161">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="1f0af-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="1f0af-162">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="1f0af-163">Пользователь конференции может звонить только в страны и регионы зоны [А,](audio-conferencing-zones.md)а также звонить на международные и внутренние номера.</span><span class="sxs-lookup"><span data-stu-id="1f0af-163">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="1f0af-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="1f0af-164">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="1f0af-165">Пользователь конференции может звонить только в страны и регионы зоны [А,](audio-conferencing-zones.md)а этот пользователь может звонить только на внутренний номер ННР.</span><span class="sxs-lookup"><span data-stu-id="1f0af-165">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="1f0af-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="1f0af-166">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="1f0af-167">Пользователь конференции может звонить только в страны и регионы зоны [А,](audio-conferencing-zones.md)а также не может делать исходящие звонки на номера ННР, кроме экстренных.</span><span class="sxs-lookup"><span data-stu-id="1f0af-167">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
