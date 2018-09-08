---
title: Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы управляют тем, как организаторы могут использовать бесплатные номера для их собраний.
ms.openlocfilehash: b438ee16135485a79458869858c52dd35bafa560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885174"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="90d5a-103">Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="90d5a-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="90d5a-104">Для получения информации об отключении бесплатных номеров для пользователей Teams см.  [Отключение бесплатных номеров для определенных пользователей Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="90d5a-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="90d5a-105">Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.</span><span class="sxs-lookup"><span data-stu-id="90d5a-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="90d5a-106">По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="90d5a-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="90d5a-107">Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами.</span><span class="sxs-lookup"><span data-stu-id="90d5a-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="90d5a-108">Если бесплатные номера отключены для определенного организатора</span><span class="sxs-lookup"><span data-stu-id="90d5a-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="90d5a-109">Бесплатный номер не будет включен в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="90d5a-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="90d5a-110">Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="90d5a-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="90d5a-111">Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации.</span><span class="sxs-lookup"><span data-stu-id="90d5a-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="90d5a-112">Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="90d5a-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="90d5a-113">При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний.</span><span class="sxs-lookup"><span data-stu-id="90d5a-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="90d5a-114">Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров.</span><span class="sxs-lookup"><span data-stu-id="90d5a-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="90d5a-115">Отключение бесплатных номеров для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="90d5a-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="90d5a-116">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="90d5a-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="90d5a-117">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="90d5a-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="90d5a-118">Снимите флажок **Разрешить использование бесплатных номеров для присоединения к собраниям этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="90d5a-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="90d5a-119">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="90d5a-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="90d5a-120">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="90d5a-120">**Using PowerShell**</span></span>  

<span data-ttu-id="90d5a-121">Можно использовать параметр AllowTollFreeDialIn Set-CsOnlineDialInConferencingUser командлета Set-CsOnlineDialInConferencingUser, чтобы включить или отключить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="90d5a-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="90d5a-122">Например:</span><span class="sxs-lookup"><span data-stu-id="90d5a-122">For example:</span></span> 

 - <span data-ttu-id="90d5a-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="90d5a-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
