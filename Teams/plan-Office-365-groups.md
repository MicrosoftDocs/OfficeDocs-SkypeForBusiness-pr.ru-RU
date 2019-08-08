---
title: Планирование использования групп Office 365 при создании команд в Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Ознакомьтесь с решениями, которые следует принимать при планировании групп Office 365, таких как выбор общедоступных и закрытых групп, использование клиента Teams или веб-консоли администрирования Office 365, а также обучение команд с помощью бесед.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b23525181de02cfe8498aa68db5c6c34e9feaded
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237435"
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="e0049-103">Планирование использования групп Office 365 при создании команд в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e0049-103">Plan for Office 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="e0049-104">Если вы планируете работать с Группами Office 365 или создавать команды, определите, для чего будет использоваться команда, кому нужен доступ к ней и какого результата следует достичь.</span><span class="sxs-lookup"><span data-stu-id="e0049-104">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="e0049-105">Особое внимание уделите числу создаваемых каналов, так как слишком сильное дробление контента (то есть разнесение его по большому числу каналов) быстро утомляет людей.</span><span class="sxs-lookup"><span data-stu-id="e0049-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="e0049-106">Существует два сценария, гарантированно инициирующих обсуждение Групп Office 365 и их взаимодействия с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0049-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="e0049-107">Прежде всего, так как у пользователей могут быть инвестиции в группы, в настоящее время поддерживаются как общедоступные, так и закрытые группы менее чем 5000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="e0049-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="e0049-108">Как упоминалось ранее, вы хотите управлять членством пользователей в команде с помощью клиента Teams, а не веб-консоли администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="e0049-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="e0049-109">Если вы используете этот сценарий, если люди используются для цепочек бесед в группах Office 365, важно отметить, что беседа группы по сути является электронной почтой, а не сообщением чата в канале Teams.</span><span class="sxs-lookup"><span data-stu-id="e0049-109">Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="e0049-110">Сообщите людям об этом различии и порекомендуйте освоить более гибкий формат сообщений чата в Teams вместо электронной почты на базе Outlook или OWA.</span><span class="sxs-lookup"><span data-stu-id="e0049-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="e0049-111">Во-вторых, для клиентов, не имеющих групп в Office 365, их можно создать с помощью портала администрирования Office 365, веб-клиента или классического клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="e0049-111">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients.</span></span> <span data-ttu-id="e0049-112">Как уже было указано ранее, в дальнейшем управлять членством в группе Office 365 следует с помощью клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="e0049-112">As mentioned previously, manage all future membership to the Office 365 Group using the Teams client.</span></span> <span data-ttu-id="e0049-113">Так как участники группы также определяют членство в группах Office 365, необходимо подготовить пользователей к этому изменению.</span><span class="sxs-lookup"><span data-stu-id="e0049-113">Since membership to a team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="e0049-114">Соблюдение в Teams политики именования Групп Office 365 (в закрытой предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="e0049-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="e0049-115">Любая политика именования для Групп Office 365, настроенная вашим администратором, применяется к Teams, когда пользователи создают или изменяют имена команд.</span><span class="sxs-lookup"><span data-stu-id="e0049-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="e0049-116">Сюда входят такие аспекты, как обязательные префиксы или суффиксы, а также исключение запрещенных слов.</span><span class="sxs-lookup"><span data-stu-id="e0049-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="e0049-117">Эта функция реализована в закрытой предварительной версии, поэтому если вы не участвуете в соответствующей программе, Teams пока что не будет соблюдать эту политику именования.</span><span class="sxs-lookup"><span data-stu-id="e0049-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="e0049-118">Дополнительные сведения см. в статье [Политика именования для Групп Office 365 в Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span><span class="sxs-lookup"><span data-stu-id="e0049-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="e0049-119">В следующих статьях удобно найти содержимое о готовности и внедрении для групп Office 365:</span><span class="sxs-lookup"><span data-stu-id="e0049-119">The following articles are a good place to find readiness and adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="e0049-120">Дополнительные возможности работы с группами в Outlook</span><span class="sxs-lookup"><span data-stu-id="e0049-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="e0049-121">Добавление и удаление участников из групп Office 365 с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0049-121">Add or remove members from Office 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="e0049-122">Восстановление удаленной группы Office 365</span><span class="sxs-lookup"><span data-stu-id="e0049-122">Restore a deleted Office 365 Group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
