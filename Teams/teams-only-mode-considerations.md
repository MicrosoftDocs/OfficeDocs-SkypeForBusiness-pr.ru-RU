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
description: Администратор может узнать, как подготовиться к обновлению до режима "Только Microsoft Teams" в Центре администрирования Microsoft Teams.
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
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460999"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="32a10-103">Сведения о режиме "Только Teams"</span><span class="sxs-lookup"><span data-stu-id="32a10-103">Teams Only mode considerations</span></span>

<span data-ttu-id="32a10-104">Администраторы Microsoft 365 или Office 365 могут обновить отдельных пользователей или весь клиент до режима Teams Only.</span><span class="sxs-lookup"><span data-stu-id="32a10-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

<span data-ttu-id="32a10-105">Переход в режим "Только в Teams" предоставляет пользователям все преимущества Microsoft Teams, концентратора для командной работы в Microsoft 365 или Office 365 с помощью одного клиента.</span><span class="sxs-lookup"><span data-stu-id="32a10-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="32a10-106">Пользователи в режиме "Только Teams" будут получать все звонки и чаты в Teams, независимо от того, использует ли отправитель Skype для бизнеса или Teams, и получают поддержку во время общения и федерации.</span><span class="sxs-lookup"><span data-stu-id="32a10-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="32a10-107">Хотя тысячи клиентов успешно обновились до Microsoft Teams, существуют факторы, которые могут повлиять на временную шкалу обновления и пользовательский интерфейс в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="32a10-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="32a10-108">Для максимального удобства пользователей сначала убедитесь, что Teams соответствует вашим потребностям для связи и совместной работы, а ваша сеть готова поддерживать Teams, после чего реализуйте свой план подготовки пользователей, прежде чем переводить их на Teams.</span><span class="sxs-lookup"><span data-stu-id="32a10-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="32a10-109">Если вы только начинаете планирование обновления, обязательно просмотрите наше руководство по обновлению [Microsoft Teams](upgrade-start-here.md) в начале работы.</span><span class="sxs-lookup"><span data-stu-id="32a10-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="32a10-110">**Вопросы сосуществования:** организации, уже использующие Skype для бизнеса Online и (или) Skype для бизнеса Server, могут представить Teams в своей среде в темпе, который соответствует их потребностям.</span><span class="sxs-lookup"><span data-stu-id="32a10-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="32a10-111">Организации по мере необходимости могут постепенно размывать Teams на нужные группы пользователей, а пользователи, которые используют Teams, могут общаться с пользователями Skype для бизнеса и наоборот.</span><span class="sxs-lookup"><span data-stu-id="32a10-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="32a10-112">Для управления этим интерфейсом администраторы используют режимы сосуществования, определяющие пользовательский интерфейс клиента, маршрутику входящих чатов и звонков, а также режимы запланированных новых собраний в Teams или Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32a10-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="32a10-113">Пользователи могут федерироваться с пользователями в других организациях, если они будут обновлены до **Teams;** однако оптимальный вариант предоставляется в том случае, если оба пользователя используют Teams.</span><span class="sxs-lookup"><span data-stu-id="32a10-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="32a10-114">Пользователи, которые обновлены до Teams, по-прежнему могут присоединяться к собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32a10-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="32a10-115">Дополнительные сведения о сосуществовании и сосуществовании в [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md)и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32a10-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="32a10-116">Дополнительные сведения о Teams и Skype (для потребителей) см. в [teams и Skype для interoperability.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="32a10-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="32a10-117">**Особенности работы пользователей.** Некоторые сценарии для пользователей постоянно совершенствуются, и администраторы могут временно отложить обновление некоторых пользователей при обновлении других пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="32a10-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="32a10-118">В частности, мы по-прежнему работаем над решением сценариев для пользователей, основное устройство которых основано на VDI.</span><span class="sxs-lookup"><span data-stu-id="32a10-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="32a10-119">Для объявлений сайтов отслеживайте [план развития Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="32a10-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="32a10-120">Перед переходом в режим "Только Teams" необходимо заменить или обновить устройства, которые не поддерживают Teams.</span><span class="sxs-lookup"><span data-stu-id="32a10-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="32a10-121">**Помните:** переход на Teams — больше, чем техническая миграция.</span><span class="sxs-lookup"><span data-stu-id="32a10-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="32a10-122">Успешное обновление оценивает как техническую готовность, так и готовность конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="32a10-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="32a10-123">Чтобы получить дополнительные сведения о планировании обновления до [Teams,](upgrade-framework.md) просмотрите наше руководство по обновлению Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="32a10-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
