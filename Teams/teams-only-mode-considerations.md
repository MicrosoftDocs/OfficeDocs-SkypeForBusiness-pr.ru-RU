---
title: Сведения о режиме "Только Teams"
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Администратор может узнать, как подготовиться к обновлению Microsoft Teams режиме только в Microsoft Teams администрирования.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239016"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="3b213-103">Сведения о режиме "Только Teams"</span><span class="sxs-lookup"><span data-stu-id="3b213-103">Teams Only mode considerations</span></span>

<span data-ttu-id="3b213-104">Администраторы Microsoft 365 или Office 365 могут перейти в режим только для отдельных пользователей или Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="3b213-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3b213-105">Обновление до Teams только для пользователей предоставляет пользователям все преимущества Microsoft Teams , концентратора для командной работы в Microsoft 365 или Office 365 с помощью одного клиента.</span><span class="sxs-lookup"><span data-stu-id="3b213-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="3b213-106">Пользователи в Teams режиме "Только" будут получать все звонки и чаты в Teams, независимо от того, какой отправитель использует Skype для бизнеса или Teams, и получают поддержку для общения и федерации.</span><span class="sxs-lookup"><span data-stu-id="3b213-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="3b213-107">Хотя тысячи клиентов успешно обновились до Microsoft Teams, существуют факторы, которые могут повлиять на временную шкалу обновления и пользовательский интерфейс организации.</span><span class="sxs-lookup"><span data-stu-id="3b213-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="3b213-108">Для максимального удобства пользователей сначала убедитесь, что Teams соответствует вашим потребностям для связи и совместной работы, а ваша сеть готова поддерживать Teams, после чего реализуйте свой план подготовки пользователей, прежде чем переводить их на Teams.</span><span class="sxs-lookup"><span data-stu-id="3b213-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3b213-109">Если вы только начинаете планирование обновления, обязательно просмотрите наше руководство по Microsoft Teams [обновлению.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="3b213-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="3b213-110">**Вопросы сосуществования.** Организации, уже использующие Skype для бизнеса Online и Skype для бизнеса Server могут внедрять Teams в свою среду в темпе, который соответствует их потребностям.</span><span class="sxs-lookup"><span data-stu-id="3b213-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="3b213-111">Организации могут по мере необходимости постепенно Teams к нужному набору пользователей, а пользователи, Teams могут общаться с пользователями, Skype для бизнеса и наоборот.</span><span class="sxs-lookup"><span data-stu-id="3b213-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="3b213-112">Для управления этим интерфейсом администраторы используют режимы совместной работы, определяющие клиентский интерфейс пользователя, поведение маршрутизов входящих чатов и звонков, а также способ Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3b213-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="3b213-113">Пользователи могут федерироваться с пользователями в других организациях, если пользователь обновлен до **Teams только**; однако оптимальный вариант предоставляется в том случае, если оба пользователя используют Teams.</span><span class="sxs-lookup"><span data-stu-id="3b213-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="3b213-114">Пользователи, обновленные до Teams, по-прежнему могут присоединяться Skype для бизнеса собраниям.</span><span class="sxs-lookup"><span data-stu-id="3b213-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3b213-115">Дополнительные сведения о сосуществовании можно найти в Microsoft Teams и Skype для бизнеса [совместной работы.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="3b213-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="3b213-116">Дополнительные сведения о Teams и Skype (потребительские) см. в Teams и [Skype.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="3b213-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="3b213-117">**Особенности работы** с пользователями. Некоторые сценарии по-прежнему находятся в процессе развития, и администраторы могут временно отложить обновление некоторых пользователей при обновлении других пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="3b213-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="3b213-118">В частности, мы по-прежнему работаем над решением сценариев для пользователей, основное устройство которых основано на VDI.</span><span class="sxs-lookup"><span data-stu-id="3b213-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="3b213-119">Для объявлений на сайте отслеживайте Microsoft 365 [развития](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="3b213-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="3b213-120">Перед переходом в Teams режиме необходимо заменить или обновить устройства, которые не поддерживают Teams.</span><span class="sxs-lookup"><span data-stu-id="3b213-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3b213-121">**Помните:** переход к Teams — это не просто техническая миграция.</span><span class="sxs-lookup"><span data-stu-id="3b213-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="3b213-122">Успешное обновление оценивает как техническую готовность, так и готовность конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b213-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="3b213-123">Дополнительные сведения о планировании [](upgrade-framework.md) Skype для бизнеса обновлении до Teams. в этой Teams.</span><span class="sxs-lookup"><span data-stu-id="3b213-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
