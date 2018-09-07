---
title: Отключение бесплатных номеров для определенных групп пользователей
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут управлять организаторов использование бесплатных номеров для их собраний.
ms.openlocfilehash: 8fafe87823308035d2626d891ae12b72c2bcfeca
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23852159"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="df62f-103">Отключение бесплатных номеров для определенных групп пользователей</span><span class="sxs-lookup"><span data-stu-id="df62f-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="df62f-104">Если ваша организация имеет бесплатных номеров в его Bridge конференц-связи Microsoft звук, можно разрешить или запретить их использование в собраниях конкретных организаторов.</span><span class="sxs-lookup"><span data-stu-id="df62f-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="df62f-105">По умолчанию все пользователи в вашей организации включены по использованию бесплатных номеров, что означает, что эти номера при наличии, можно использовать участниками на присоединение к собраниям их.</span><span class="sxs-lookup"><span data-stu-id="df62f-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="df62f-106">Если это не желаемое поведение для некоторых пользователей в вашей организации, вы можете запретить определенными пользователями с помощью этих номеров в свои собрания с помощью бесплатных номеров включение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="df62f-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="df62f-107">Когда бесплатных номеров отключены для данного организатора:</span><span class="sxs-lookup"><span data-stu-id="df62f-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="df62f-108">Бесплатный номер больше не требуется включить в его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="df62f-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="df62f-109">Обслуживание бесплатных номеров больше не отображается на странице «Найдите местный номер», которое содержит ссылку на его или ее собрания приглашает.</span><span class="sxs-lookup"><span data-stu-id="df62f-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="df62f-110">Участники не сможет присоединиться к собранию данного организатора, если они набрать любой бесплатный номер организации.</span><span class="sxs-lookup"><span data-stu-id="df62f-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="df62f-111">Автоматически будет выполнено всех собраний организатора и телефоны будет удален из них.</span><span class="sxs-lookup"><span data-stu-id="df62f-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="df62f-112">Это будет отправить все приглашения электронной почты организатора всем участникам собраниям.</span><span class="sxs-lookup"><span data-stu-id="df62f-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="df62f-113">Участники могут продолжать присоединения к собраниям картинок, с помощью платные номера.</span><span class="sxs-lookup"><span data-stu-id="df62f-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="df62f-114">Отключение бесплатных номеров для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="df62f-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="df62f-115">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="df62f-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="df62f-116">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="df62f-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="df62f-117">Рядом с пунктом **Звук конференц-связи**нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="df62f-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="df62f-118">Отключите **включают бесплатные номера в приглашений на собрание из этого пользователя**.</span><span class="sxs-lookup"><span data-stu-id="df62f-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="df62f-119">Нажмите кнопку **Сохраните.**</span><span class="sxs-lookup"><span data-stu-id="df62f-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="df62f-120">**С помощью PowerShell**</span><span class="sxs-lookup"><span data-stu-id="df62f-120">**Using PowerShell**</span></span>  

<span data-ttu-id="df62f-121">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="df62f-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
