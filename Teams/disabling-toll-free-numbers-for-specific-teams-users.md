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
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут управлять тем, как организаторы используют бесплатные номера для своих собраний.
ms.openlocfilehash: 6fd415575110f9c6ae1dcf7b4fc006213a23cedd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232629"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="c1218-103">Отключение бесплатных номеров для отдельных пользователей Teams</span><span class="sxs-lookup"><span data-stu-id="c1218-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="c1218-104">Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.</span><span class="sxs-lookup"><span data-stu-id="c1218-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="c1218-105">По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="c1218-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="c1218-106">Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами.</span><span class="sxs-lookup"><span data-stu-id="c1218-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="c1218-107">Если бесплатные номера отключены для определенного организатора</span><span class="sxs-lookup"><span data-stu-id="c1218-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="c1218-108">Бесплатный номер не будет включен в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="c1218-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c1218-109">Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="c1218-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c1218-110">Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации.</span><span class="sxs-lookup"><span data-stu-id="c1218-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="c1218-111">Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="c1218-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="c1218-112">При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний.</span><span class="sxs-lookup"><span data-stu-id="c1218-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="c1218-113">Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров.</span><span class="sxs-lookup"><span data-stu-id="c1218-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="c1218-114">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="c1218-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="c1218-115">Из **центра администрирования группами Майкрософт**:</span><span class="sxs-lookup"><span data-stu-id="c1218-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="c1218-116">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c1218-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c1218-117">Щелкните **Изменить** рядом с элементом **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="c1218-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="c1218-118">Значение **включают бесплатные номера в приглашении на собрание из этого пользователя** **из системы**.</span><span class="sxs-lookup"><span data-stu-id="c1218-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="c1218-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c1218-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="c1218-120">**Использование PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1218-120">**Using PowerShell**</span></span>  

<span data-ttu-id="c1218-121">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c1218-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
