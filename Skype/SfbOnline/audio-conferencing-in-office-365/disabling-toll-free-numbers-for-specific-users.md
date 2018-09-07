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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы управляют тем, как организаторы могут использовать бесплатные номера для их собраний.
ms.openlocfilehash: 6b441d8c136375628243d77280b6a32768b0a590
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860724"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="f7af5-103">Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f7af5-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="f7af5-104">Для получения информации об отключении бесплатных номеров для пользователей Teams см.  [Отключение бесплатных номеров для определенных пользователей Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="f7af5-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="f7af5-105">Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.</span><span class="sxs-lookup"><span data-stu-id="f7af5-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="f7af5-106">По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="f7af5-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="f7af5-107">Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами.</span><span class="sxs-lookup"><span data-stu-id="f7af5-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="f7af5-108">Если бесплатные номера отключены для определенного организатора</span><span class="sxs-lookup"><span data-stu-id="f7af5-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="f7af5-109">Бесплатный номер не будет включен в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="f7af5-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f7af5-110">Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="f7af5-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f7af5-111">Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации.</span><span class="sxs-lookup"><span data-stu-id="f7af5-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="f7af5-112">Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="f7af5-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="f7af5-113">При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний.</span><span class="sxs-lookup"><span data-stu-id="f7af5-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="f7af5-114">Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров.</span><span class="sxs-lookup"><span data-stu-id="f7af5-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="f7af5-115">Отключение бесплатных номеров для определенных пользователей</span><span class="sxs-lookup"><span data-stu-id="f7af5-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="f7af5-116">В **центре администрирования Skype для бизнеса** на панели навигации слева перейдите в раздел **Аудиоконференции** > **Пользователи**, затем выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7af5-116">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Dial-in users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="f7af5-117">На панели действий нажмите **Правка**.</span><span class="sxs-lookup"><span data-stu-id="f7af5-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="f7af5-118">Снимите флажок **Разрешить использование бесплатных номеров для присоединения к собраниям этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f7af5-118">**Allow using toll-free numbers in the Microsoft bridge of your organization to join the meetings of this user**</span></span> 
 
4. <span data-ttu-id="f7af5-119">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f7af5-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="f7af5-120">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f7af5-120">**Using PowerShell**</span></span>  

<span data-ttu-id="f7af5-121">Можно использовать параметр AllowTollFreeDialIn Set-CsOnlineDialInConferencingUser командлета Set-CsOnlineDialInConferencingUser, чтобы включить или отключить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="f7af5-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="f7af5-122">Например:</span><span class="sxs-lookup"><span data-stu-id="f7af5-122">For example:</span></span> 

 - <span data-ttu-id="f7af5-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="f7af5-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
