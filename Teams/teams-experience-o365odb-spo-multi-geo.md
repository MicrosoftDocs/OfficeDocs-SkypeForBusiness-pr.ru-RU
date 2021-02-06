---
title: Возможности Teams в среде с поддержкой нескольких служб Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: В этой статье вы узнаете об использовании Teams в среде с поддержкой нескольких служб Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122249"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="13716-103">Возможности Teams в многоязной области Microsoft 365 с поддержкой нескольких геолокации</span><span class="sxs-lookup"><span data-stu-id="13716-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="13716-104">Microsoft Teams — это групповой чат, центр для командной работы в Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="13716-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="13716-105">Она наряду со службой SharePoint Online и OneDrive для бизнеса, а также службой Групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="13716-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="13716-106">В мульти географической области OneDrive для бизнеса или SharePoint Online, в которой клиент распространяется на множество географических объектов, таких как Северная Америка, Европа и Австралия, взаимодействие с файлами является многофационным, поэтому совместная работа с файлами в Teams также может быть мульти geo-aware.</span><span class="sxs-lookup"><span data-stu-id="13716-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="13716-107">Эта функция является основным средством работы Teams с surface-файлами, которые находятся в различных регионах.</span><span class="sxs-lookup"><span data-stu-id="13716-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="13716-108">Это также относится к файлам OneNote и вики-сайтам.</span><span class="sxs-lookup"><span data-stu-id="13716-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="13716-109">Например, в клиенте Contoso, где Европа расположена как спутниковый геосем, а в Северной  Америке — в качестве центрального геоупорядочества, европейский спутниковый пользователь будет видеть свои файлы OneDrive на вкладке "Файлы" в левой области, хотя они находятся в Европе, а сша — в качестве центрального расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="13716-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="13716-110">Кроме того, пользователь может получить доступ к  файлам, которые использовались последними, в области "Последние".</span><span class="sxs-lookup"><span data-stu-id="13716-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="13716-111">Последние файлы могут включать файлы, общий доступ к ним от пользователей из других геолокации.</span><span class="sxs-lookup"><span data-stu-id="13716-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="13716-112">Сайт SharePoint группы также может быть частью с учетом нескольких геоустойок.</span><span class="sxs-lookup"><span data-stu-id="13716-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="13716-113">То есть, если европейский спутниковый пользователь создает команду, соответствующий сайт SharePoint будет создан в Европе.</span><span class="sxs-lookup"><span data-stu-id="13716-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="13716-114">Связанные с командой файлы будут храниться в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="13716-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="13716-115">Все последующие действия, такие как отправка или редактирование файла, будут храниться в европейском расположении, сохраняя обещания о размещении данных для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="13716-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="13716-116">Так как мульти geo tenancy — это один глобальный клиент, во время @упоминаний спутниковые пользователи смогут видеть своих коллег со всего мира, где бы они ни были.</span><span class="sxs-lookup"><span data-stu-id="13716-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="13716-117">Беседы в чатах, сообщениях каналов, заметках к мгновенным сообщениям и чатах в Teams не могут быть частью с несколькими геосканами и хранятся только в центральном расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="13716-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="13716-118">Обычно беседы чата не применяются к потребностям места проживания данных.</span><span class="sxs-lookup"><span data-stu-id="13716-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="13716-119">Дополнительные сведения см. [в сведениях о расположении данных в Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="13716-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="13716-120">Дополнительные сведения о multi-Geo можно найти на странице [microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="13716-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
