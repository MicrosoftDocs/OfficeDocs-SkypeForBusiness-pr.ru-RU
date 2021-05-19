---
title: Ограничения на исходящие звонки — аудиоконференция & звонками по ЗВОНКОВ по ЗВОНКОВ по ННР
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
description: Администраторы могут управлять типами аудиоконференций и пользовательскими звонками по STN, которые могут делать пользователи.
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526732"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="e16df-103">Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП</span><span class="sxs-lookup"><span data-stu-id="e16df-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="e16df-104">Администраторы могут использовать элементы управления исходящие звонки для ограничения типа аудиоконференций и звонков по телефонной сети общего пользования (СТСК), которые могут делать пользователи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e16df-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="e16df-105">Элементы управления исходящие звонки можно применять для каждого пользователя или клиента, а также предоставлять следующие два средства управления для независимого ограничения каждого типа исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="e16df-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="e16df-106">По умолчанию оба элемента управления разрешают международные и внутренние исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="e16df-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="e16df-107">Управления</span><span class="sxs-lookup"><span data-stu-id="e16df-107">Control</span></span>|<span data-ttu-id="e16df-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e16df-108">Description</span></span>|<span data-ttu-id="e16df-109">Параметры элемента управления</span><span class="sxs-lookup"><span data-stu-id="e16df-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e16df-110">Вызовы аудиоконференции по ТСОП</span><span class="sxs-lookup"><span data-stu-id="e16df-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="e16df-111">Ограничивает тип исходящих</span><span class="sxs-lookup"><span data-stu-id="e16df-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="e16df-112">вызовов, которые разрешено выполнять</span><span class="sxs-lookup"><span data-stu-id="e16df-112">calls that are allowed from within</span></span> </br><span data-ttu-id="e16df-113">во время собраний, организованных пользователем.</span><span class="sxs-lookup"><span data-stu-id="e16df-113">meetings organized by a user.</span></span>|<span data-ttu-id="e16df-114">Назначение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e16df-114">Any destination (default)</span></span></br><span data-ttu-id="e16df-115">В той же стране или регионе, где был организатор</span><span class="sxs-lookup"><span data-stu-id="e16df-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="e16df-116">[Только страны или регионы зоны A](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="e16df-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="e16df-117">Не разрешайте</span><span class="sxs-lookup"><span data-stu-id="e16df-117">Don't allow</span></span>|
|<span data-ttu-id="e16df-118">Звонки через ОКП для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="e16df-118">End-user PSTN calls</span></span>|<span data-ttu-id="e16df-119">Ограничивает тип вызовов,</span><span class="sxs-lookup"><span data-stu-id="e16df-119">Restricts the type of calls</span></span> </br><span data-ttu-id="e16df-120">доступных пользователю.</span><span class="sxs-lookup"><span data-stu-id="e16df-120">that can be made by a user.</span></span>|<span data-ttu-id="e16df-121">Международные и внутренние (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e16df-121">International and Domestic (default)</span></span></br><span data-ttu-id="e16df-122">Внутренний</span><span class="sxs-lookup"><span data-stu-id="e16df-122">Domestic</span></span></br><span data-ttu-id="e16df-123">Нет</span><span class="sxs-lookup"><span data-stu-id="e16df-123">None</span></span>|

<span data-ttu-id="e16df-124">Чтобы узнать, какие страны и регионы считаются зонами A, см. зоны страны и региона для [аудиоконференции.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="e16df-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e16df-125">Звонок считается внутренним, если набраный номер находится в той же стране, где настроена Microsoft 365 или Office 365 для организатора собрания (в случае аудиоконференции) или конечного пользователя (в случае звонков по ННП для конечного пользователя).</span><span class="sxs-lookup"><span data-stu-id="e16df-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="e16df-126">Ограничение исходящих вызовов аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e16df-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="e16df-127">![Логотип Microsoft Teams с ](media/teams-logo-30x30.png) **помощью Microsoft Teams центра администрирования**</span><span class="sxs-lookup"><span data-stu-id="e16df-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e16df-128">В области навигации слева выберите **Пользователи** и в списке доступных пользователей выберите отображаемого имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="e16df-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="e16df-129">Рядом с **аудиоконференцией** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e16df-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="e16df-130">В **диалоговом окте**"Выводить из собраний" выберите нужный вариант ограничения на набор номеров.</span><span class="sxs-lookup"><span data-stu-id="e16df-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="e16df-131">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e16df-131">Select **Save**.</span></span>

<span data-ttu-id="e16df-132">![Значок с логотипом Skype для бизнеса](media/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="e16df-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="e16df-133">В **Skype для бизнеса** администрирования на левой навигации перейдите в меню Пользователи аудиоконференции , а затем выберите пользователя в списке  >  доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e16df-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e16df-134">В области действий выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e16df-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="e16df-135">В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.</span><span class="sxs-lookup"><span data-stu-id="e16df-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![Параметры ограничения исходящих вызовов](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="e16df-137">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e16df-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e16df-138">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e16df-138">**Using PowerShell**</span></span>

<span data-ttu-id="e16df-139">Ограничения исходящие вызовы контролируются одной политикой Под названием OnlineDialOutPolicy, которая имеет атрибут ограничения для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="e16df-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="e16df-140">Эту политику нельзя изменить в соответствии с потребностями пользователя, но можно использовать предварительно заданные экземпляры политики для каждого сочетания параметров.</span><span class="sxs-lookup"><span data-stu-id="e16df-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="e16df-141">С помощью Get-CSOnlineDialOutPolicy вы можете просмотреть политики исходящие вызовы и использовать для настройки следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e16df-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="e16df-142">**Задате для политики уровень "на пользователя" с помощью следующего cmdlet**:</span><span class="sxs-lookup"><span data-stu-id="e16df-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="e16df-143">(В нем нет слова "Online", как в get.)</span><span class="sxs-lookup"><span data-stu-id="e16df-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="e16df-144">**Задать политику на уровне клиента с помощью следующего cmdlet**:</span><span class="sxs-lookup"><span data-stu-id="e16df-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="e16df-145">Эта политика будет назначена всем пользователям клиента, у которых нет назначенной политики.</span><span class="sxs-lookup"><span data-stu-id="e16df-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="e16df-146">Другие пользователи остаются в текущей политике.</span><span class="sxs-lookup"><span data-stu-id="e16df-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="e16df-147">В следующей таблице представлена общая информация о каждой политике.</span><span class="sxs-lookup"><span data-stu-id="e16df-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="e16df-148">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e16df-148">PowerShell cmdlet</span></span>|<span data-ttu-id="e16df-149">Описание</span><span class="sxs-lookup"><span data-stu-id="e16df-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="e16df-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e16df-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="e16df-151">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь также может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="e16df-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="e16df-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e16df-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="e16df-153">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять внутренние и международные исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="e16df-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e16df-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e16df-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="e16df-155">Пользователь на конференции не может звонить. Этот пользователь может звонить на международные и внутренние номера.</span><span class="sxs-lookup"><span data-stu-id="e16df-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e16df-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e16df-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="e16df-157">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e16df-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e16df-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e16df-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="e16df-159">Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="e16df-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e16df-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e16df-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="e16df-161">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e16df-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e16df-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e16df-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="e16df-163">Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.</span><span class="sxs-lookup"><span data-stu-id="e16df-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e16df-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e16df-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="e16df-165">Пользователь конференции не может исходящие телефонные вызовы, а этот пользователь может звонить только на внутренние номера ОКП.</span><span class="sxs-lookup"><span data-stu-id="e16df-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e16df-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e16df-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="e16df-167">Пользователь на конференции не может исходящие звонки, а также не может звонить на номер ПСС, кроме экстренных номеров.</span><span class="sxs-lookup"><span data-stu-id="e16df-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e16df-168">Identity='tag:DialoutCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="e16df-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="e16df-169">Пользователь конференции может звонить только в страны и регионы зоны [A,](audio-conferencing-zones.md)а также звонить на международные и внутренние номера.</span><span class="sxs-lookup"><span data-stu-id="e16df-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e16df-170">Identity='tag:DialoutCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="e16df-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="e16df-171">Пользователь конференции может звонить только в страны и регионы зоны [A,](audio-conferencing-zones.md)а этот пользователь может звонить только на внутренний номер ПСС.</span><span class="sxs-lookup"><span data-stu-id="e16df-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e16df-172">Identity='tag:DialoutCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="e16df-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="e16df-173">Пользователь конференции может звонить только в страны и регионы зоны [A,](audio-conferencing-zones.md)и этот пользователь не может звонить на номер ПСЧ, кроме экстренных номеров.</span><span class="sxs-lookup"><span data-stu-id="e16df-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
