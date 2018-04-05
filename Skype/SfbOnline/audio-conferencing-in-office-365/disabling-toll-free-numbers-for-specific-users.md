---
title: Отключение бесплатных номеров для отдельных пользователей
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Администраторы могут управлять организаторов использование бесплатных номеров для их собраний.
ms.openlocfilehash: d0b7703f4dd518caa5ffb339282c5a7bbac4daa3
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="48440-103">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="48440-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="48440-104">Если ваша организация имеет бесплатных номеров в его Bridge конференц-связи Microsoft звук, можно разрешить или запретить их использование в собраниях конкретных организаторов.</span><span class="sxs-lookup"><span data-stu-id="48440-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="48440-105">По умолчанию все пользователи в вашей организации включены по использованию бесплатных номеров, что означает, что эти номера при наличии, можно использовать участниками на присоединение к собраниям их.</span><span class="sxs-lookup"><span data-stu-id="48440-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="48440-106">Если это не желаемое поведение для некоторых пользователей в вашей организации, вы можете запретить определенными пользователями с помощью этих номеров в свои собрания с помощью бесплатных номеров включение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48440-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="48440-107">Когда бесплатных номеров отключены для данного организатора:</span><span class="sxs-lookup"><span data-stu-id="48440-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="48440-108">Бесплатный номер больше не требуется включить в его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="48440-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="48440-109">Обслуживание бесплатных номеров больше не отображается на странице «Найдите местный номер», которое содержит ссылку на его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="48440-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="48440-110">Участники не сможет присоединиться к собранию данного организатора, если они набрать любой бесплатный номер организации.</span><span class="sxs-lookup"><span data-stu-id="48440-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="48440-111">Автоматически будет выполнено всех собраний организатора и телефоны будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="48440-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="48440-112">Это будет отправить все приглашения электронной почты организатора всем участникам собраниям.</span><span class="sxs-lookup"><span data-stu-id="48440-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="48440-113">Участники могут продолжать присоединения к собраниям картинок, с помощью платные номера.</span><span class="sxs-lookup"><span data-stu-id="48440-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="48440-114">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="48440-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="48440-115">**Использование групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="48440-115">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="48440-116">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="48440-116">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="48440-117">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="48440-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="48440-118">Щелкните меню рядом с пунктом **Мостов конференции**и нажмите кнопку **Изменить** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="48440-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="48440-119">В области **конференции bridge поставщика** отключите **Разрешить использование бесплатных номеров в bridge конференц-связи организации для присоединения к собраниям этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="48440-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="48440-120">Нажмите кнопку **применения.**</span><span class="sxs-lookup"><span data-stu-id="48440-120">Click **Apply.**</span></span> 

<span data-ttu-id="48440-121">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="48440-121">**Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="48440-122">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="48440-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="48440-123">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="48440-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="48440-124">Снимите флажок **Разрешить использование бесплатных номеров для присоединения к собраниям этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="48440-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="48440-125">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="48440-125">Click **Save**.</span></span> 
 
<span data-ttu-id="48440-126">**С помощью PowerShell**</span><span class="sxs-lookup"><span data-stu-id="48440-126">**Using PowerShell**</span></span>  

<span data-ttu-id="48440-127">Параметр AllowTollFreeDialIn командлета Set-CsOnlineDialInConferencingUser можно использовать для включения или отключения данного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="48440-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="48440-128">Например:</span><span class="sxs-lookup"><span data-stu-id="48440-128">For example:</span></span> 

 - <span data-ttu-id="48440-129">SET-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="48440-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
