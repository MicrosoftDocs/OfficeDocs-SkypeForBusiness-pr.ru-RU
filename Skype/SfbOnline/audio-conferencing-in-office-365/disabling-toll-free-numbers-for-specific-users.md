---
title: Отключение бесплатных номеров для конкретных Скайп для бизнеса в Интернет пользователей
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: Администраторы могут управлять организаторов использование бесплатных номеров для их собраний.
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490548"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="c8811-103">Отключение бесплатных номеров для конкретных Скайп для бизнеса в Интернет пользователей</span><span class="sxs-lookup"><span data-stu-id="c8811-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="c8811-104">Сведения о отключение номеров без использования средства для группы пользователей видеть [Отключение бесплатных номеров для определенных групп пользователей](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="c8811-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="c8811-105">Если ваша организация имеет бесплатных номеров в его Bridge конференц-связи Microsoft звук, можно разрешить или запретить их использование в собраниях конкретных организаторов.</span><span class="sxs-lookup"><span data-stu-id="c8811-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="c8811-106">По умолчанию все пользователи в вашей организации включены по использованию бесплатных номеров, что означает, что эти номера при наличии, можно использовать участниками на присоединение к собраниям их.</span><span class="sxs-lookup"><span data-stu-id="c8811-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="c8811-107">Если это не желаемое поведение для некоторых пользователей в вашей организации, вы можете запретить определенными пользователями с помощью этих номеров в свои собрания с помощью бесплатных номеров включение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c8811-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="c8811-108">Когда бесплатных номеров отключены для данного организатора:</span><span class="sxs-lookup"><span data-stu-id="c8811-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="c8811-109">Бесплатный номер больше не требуется включить в его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="c8811-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c8811-110">Обслуживание бесплатных номеров больше не отображается на странице «Найдите местный номер», которое содержит ссылку на его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="c8811-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c8811-111">Участники не сможет присоединиться к собранию данного организатора, если они набрать любой бесплатный номер организации.</span><span class="sxs-lookup"><span data-stu-id="c8811-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="c8811-112">Автоматически будет выполнено всех собраний организатора и телефоны будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="c8811-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="c8811-113">Это будет отправить все приглашения электронной почты организатора всем участникам собраниям.</span><span class="sxs-lookup"><span data-stu-id="c8811-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="c8811-114">Участники могут продолжать присоединения к собраниям картинок, с помощью платные номера.</span><span class="sxs-lookup"><span data-stu-id="c8811-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="c8811-115">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="c8811-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="c8811-116">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8811-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="c8811-117">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="c8811-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="c8811-118">Снимите флажок **Разрешить использование бесплатных номеров для присоединения к собраниям этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="c8811-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="c8811-119">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="c8811-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="c8811-120">**С помощью PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c8811-120">**Using PowerShell**</span></span>  

<span data-ttu-id="c8811-121">Параметр AllowTollFreeDialIn командлета Set-CsOnlineDialInConferencingUser можно использовать для включения или отключения данного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c8811-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="c8811-122">Например:</span><span class="sxs-lookup"><span data-stu-id="c8811-122">For example:</span></span> 

 - <span data-ttu-id="c8811-123">SET-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="c8811-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
