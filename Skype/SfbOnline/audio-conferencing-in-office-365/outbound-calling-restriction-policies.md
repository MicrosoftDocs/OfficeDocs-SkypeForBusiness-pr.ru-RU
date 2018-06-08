---
title: Исходящих вызовов политики ограниченного использования программ для вызовов ТСОП аудиоконференции и пользователей
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут управлять тип звукового конференц-связи и конечного пользователя вызовы в ТСОП, которые могут создаваться пользователями.
ms.openlocfilehash: 0533a15d6c60720f37c859f110b30af617d95774
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703427"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="465eb-103">Исходящих вызовов политики ограниченного использования программ для вызовов ТСОП аудиоконференции и пользователей</span><span class="sxs-lookup"><span data-stu-id="465eb-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="465eb-104">С правами администратора можно использовать элементы управления исходящих вызовов для ограничения тип звукового конференц-связи и конечного пользователя вызовы в ТСОП, которые могут создаваться пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="465eb-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="465eb-105">Элементы управления исходящих вызовов могут применяться отдельно для каждого пользователя и предоставляют следующие два элемента управления для ограничения каждого типа исходящие вызовы независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="465eb-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="465eb-106">По умолчанию устанавливаются оба элемента управления, Разрешить исходящие вызовы в международных и внутренние.</span><span class="sxs-lookup"><span data-stu-id="465eb-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="465eb-107">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="465eb-107">Control</span></span>|<span data-ttu-id="465eb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="465eb-108">Description</span></span>|<span data-ttu-id="465eb-109">Параметры элемента управления</span><span class="sxs-lookup"><span data-stu-id="465eb-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="465eb-110">Голосовые вызовы ТСОП конференц-связи</span><span class="sxs-lookup"><span data-stu-id="465eb-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="465eb-111">Ограничивает тип исходящего</span><span class="sxs-lookup"><span data-stu-id="465eb-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="465eb-112">звонки, в которых разрешен изнутри</span><span class="sxs-lookup"><span data-stu-id="465eb-112">calls that are allowed from within</span></span> </br><span data-ttu-id="465eb-113">собраний, организованных пользователем.</span><span class="sxs-lookup"><span data-stu-id="465eb-113">meetings organized by a user.</span></span>|<span data-ttu-id="465eb-114">Международные и внутренний (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="465eb-114">International and Domestic (default)</span></span></br><span data-ttu-id="465eb-115">Внутренний</span><span class="sxs-lookup"><span data-stu-id="465eb-115">Domestic</span></span></br><span data-ttu-id="465eb-116">Нет</span><span class="sxs-lookup"><span data-stu-id="465eb-116">None</span></span>|
|<span data-ttu-id="465eb-117">Вызовы в ТСОП конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="465eb-117">End user PSTN calls</span></span>|<span data-ttu-id="465eb-118">Ограничивает число типа звонков</span><span class="sxs-lookup"><span data-stu-id="465eb-118">Restricts the type of calls</span></span> </br><span data-ttu-id="465eb-119">который можно внесенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="465eb-119">that can be made by a user.</span></span>|<span data-ttu-id="465eb-120">Международные и внутренний (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="465eb-120">International and Domestic (default)</span></span></br><span data-ttu-id="465eb-121">Внутренний</span><span class="sxs-lookup"><span data-stu-id="465eb-121">Domestic</span></span></br><span data-ttu-id="465eb-122">Нет</span><span class="sxs-lookup"><span data-stu-id="465eb-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="465eb-123">Вызов определяется как внутренних, если номера телефонов в стране, в качестве страны, который был установлен в Office 365 для организатора собрания (в случае аудиоконференций) или конечного пользователя (в случае вызовы в ТСОП конечного пользователя).</span><span class="sxs-lookup"><span data-stu-id="465eb-123">A call is determined to be domestic if the called phone number is in the same country as the country that has been set in Office 365 for the organizer of the meeting (in the case of audio conferencing) or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="465eb-124">Ограничить исходящие вызовы аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="465eb-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="465eb-125">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="465eb-125">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="465eb-126">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="465eb-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="465eb-127">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="465eb-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="465eb-128">Щелкните меню рядом с пунктом **Мостов конференции**и нажмите кнопку **Изменить** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="465eb-128">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="465eb-129">В области **конференции bridge поставщика** в разделе **ограничения на телефонные контакты из собраний с этим пользователем**выберите нужный вариант ограничения по телефону.</span><span class="sxs-lookup"><span data-stu-id="465eb-129">In the **Conference bridge provider** pane, under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="465eb-130">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="465eb-130">Click **Apply**.</span></span> 

<span data-ttu-id="465eb-131">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="465eb-131">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="465eb-132">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="465eb-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="465eb-133">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="465eb-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="465eb-134">В разделе **ограничения на телефонные контакты из собраний с этим пользователем**выберите нужный вариант ограничения по телефону.</span><span class="sxs-lookup"><span data-stu-id="465eb-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![Ограничения на параметры телефонные контакты](../images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="465eb-136">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="465eb-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="465eb-137">**С помощью PowerShell**</span><span class="sxs-lookup"><span data-stu-id="465eb-137">**Using PowerShell**</span></span>

<span data-ttu-id="465eb-138">Исходящий звонок ограничения управляются одну политику с именем OnlineDialOutPolicy, который имеет атрибут ограничение для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="465eb-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="465eb-139">Нельзя настроить политику, а существует предварительно заданные политики экземпляров для каждого сочетания параметров.</span><span class="sxs-lookup"><span data-stu-id="465eb-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="465eb-140">Командлет Get-CSOnlineDialOutPolicy для просмотра исходящих вызовов политик и назначьте их пользователям с помощью командлета Grant-CSDialOutPolicy.</span><span class="sxs-lookup"><span data-stu-id="465eb-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="465eb-141">(Обратите внимание, что командлет Grant не со словом «Online» как командлета Get.)</span><span class="sxs-lookup"><span data-stu-id="465eb-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="465eb-142">В следующей таблице содержится обзор каждой политики.</span><span class="sxs-lookup"><span data-stu-id="465eb-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="465eb-143">IDENTITY = «tag: DialoutCPCandPSTNInternational»</span><span class="sxs-lookup"><span data-stu-id="465eb-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="465eb-144">Пользователя в конференции можно исходящие вызовы для внутренних и международных номеров, и этот пользователь также может выполнять исходящие вызовы для внутренних и международных номеров.</span><span class="sxs-lookup"><span data-stu-id="465eb-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="465eb-145">IDENTITY = «tag: DialoutCPCDomesticPSTNInternational»</span><span class="sxs-lookup"><span data-stu-id="465eb-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="465eb-146">Пользователя в конференции можно только исходящих звонков на внутренние номера, и этот пользователь может выполнять исходящие вызовы для внутренних и международных номеров.</span><span class="sxs-lookup"><span data-stu-id="465eb-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="465eb-147">IDENTITY = «tag: DialoutCPCDisabledPSTNInternational»</span><span class="sxs-lookup"><span data-stu-id="465eb-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="465eb-148">Пользователь в конференции не может выполнять любые номера в работе. Этот пользователь может выполнять исходящие вызовы для внутренних и международных номеров.</span><span class="sxs-lookup"><span data-stu-id="465eb-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="465eb-149">IDENTITY = «tag: DialoutCPCInternationalPSTNDomestic»</span><span class="sxs-lookup"><span data-stu-id="465eb-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="465eb-150">Пользователя в конференции можно исходящие вызовы для внутренних и международных номеров и этому пользователю можно выполнять только исходящие звонки на внутренний номер PSTN.</span><span class="sxs-lookup"><span data-stu-id="465eb-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="465eb-151">IDENTITY = «tag: DialoutCPCInternationalPSTNDisabled»</span><span class="sxs-lookup"><span data-stu-id="465eb-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="465eb-152">Пользователя в конференции можно исходящие вызовы для внутренних и международных номеров, и этот пользователь не может выполнять все исходящие звонки на номер PSTN помимо аварийного номера.</span><span class="sxs-lookup"><span data-stu-id="465eb-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="465eb-153">IDENTITY = «tag: DialoutCPCandPSTNDomestic»</span><span class="sxs-lookup"><span data-stu-id="465eb-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="465eb-154">Пользователя в конференции только соединиться с внутренних телефонов и этому пользователю можно выполнять только исходящих вызовов на номера внутри страны PSTN.</span><span class="sxs-lookup"><span data-stu-id="465eb-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="465eb-155">IDENTITY = «tag: DialoutCPCDomesticPSTNDisabled»</span><span class="sxs-lookup"><span data-stu-id="465eb-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="465eb-156">Пользователя в конференции можно только исходящих звонков на внутренние номера, и этот пользователь не может выполнять все исходящие звонки на номер PSTN помимо аварийного номера.</span><span class="sxs-lookup"><span data-stu-id="465eb-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="465eb-157">IDENTITY = «tag: DialoutCPCDisabledPSTNDomestic»</span><span class="sxs-lookup"><span data-stu-id="465eb-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="465eb-158">Пользователь в конференции не может выполнять все исходящие звонки и этому пользователю можно выполнять только исходящих вызовов на номера внутри страны PSTN.</span><span class="sxs-lookup"><span data-stu-id="465eb-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="465eb-159">IDENTITY = «tag: DialoutCPCandPSTNDisabled»</span><span class="sxs-lookup"><span data-stu-id="465eb-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="465eb-160">Пользователь в конференции не может выполнять все исходящие звонки, и этот пользователь не может выполнять все исходящие звонки на номер PSTN помимо аварийного номера.</span><span class="sxs-lookup"><span data-stu-id="465eb-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
