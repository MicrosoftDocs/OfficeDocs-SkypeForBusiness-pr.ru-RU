---
title: Отключение бесплатных номеров для отдельных пользователей Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут управлять тем, как организаторы используют бесплатные номера для своих собраний.
ms.openlocfilehash: 158a4b31b0aaf65414af0d2119b3b6931a1f74ac
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014695"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="cbe89-103">Отключение бесплатных номеров для отдельных пользователей Teams</span><span class="sxs-lookup"><span data-stu-id="cbe89-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="cbe89-104">Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.</span><span class="sxs-lookup"><span data-stu-id="cbe89-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="cbe89-105">По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="cbe89-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="cbe89-106">Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами.</span><span class="sxs-lookup"><span data-stu-id="cbe89-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="cbe89-107">Если бесплатные номера отключены для определенного организатора</span><span class="sxs-lookup"><span data-stu-id="cbe89-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="cbe89-108">Бесплатный номер не будет включен в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="cbe89-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="cbe89-109">Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="cbe89-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="cbe89-110">Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации.</span><span class="sxs-lookup"><span data-stu-id="cbe89-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="cbe89-111">Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="cbe89-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="cbe89-112">При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний.</span><span class="sxs-lookup"><span data-stu-id="cbe89-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="cbe89-113">Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров.</span><span class="sxs-lookup"><span data-stu-id="cbe89-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="cbe89-114">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="cbe89-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="cbe89-115">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cbe89-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="cbe89-116">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cbe89-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cbe89-117">Щелкните **Изменить** рядом с элементом **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="cbe89-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="cbe89-118">Отключите настройку **Включать бесплатные номера в приглашения на собрание от этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="cbe89-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="cbe89-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cbe89-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="cbe89-120">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cbe89-120">**Using PowerShell**</span></span>  

<span data-ttu-id="cbe89-121">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="cbe89-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
