---
title: Отключение бесплатных номеров для отдельных пользователей Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут управлять тем, как организаторы используют бесплатные номера для своих собраний.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887382"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="f58df-103">Отключение бесплатных номеров для отдельных пользователей Teams</span><span class="sxs-lookup"><span data-stu-id="f58df-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="f58df-104">Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.</span><span class="sxs-lookup"><span data-stu-id="f58df-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="f58df-105">По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="f58df-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="f58df-106">Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами.</span><span class="sxs-lookup"><span data-stu-id="f58df-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="f58df-107">Если бесплатные номера отключены для определенного организатора</span><span class="sxs-lookup"><span data-stu-id="f58df-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="f58df-108">Бесплатный номер не будет включен в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="f58df-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f58df-109">Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="f58df-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f58df-110">Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации.</span><span class="sxs-lookup"><span data-stu-id="f58df-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="f58df-111">Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="f58df-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="f58df-112">При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний.</span><span class="sxs-lookup"><span data-stu-id="f58df-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="f58df-113">Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров.</span><span class="sxs-lookup"><span data-stu-id="f58df-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="f58df-114">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="f58df-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="f58df-115">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f58df-115">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f58df-116">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="f58df-116">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="f58df-117">Щелкните **Изменить** рядом с элементом **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="f58df-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="f58df-118">Отключите настройку **Включать бесплатные номера в приглашения на собрание от этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f58df-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="f58df-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f58df-119">Click **Save**.</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="f58df-120">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f58df-120">**Using PowerShell**</span></span>  

<span data-ttu-id="f58df-121">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="f58df-121">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
