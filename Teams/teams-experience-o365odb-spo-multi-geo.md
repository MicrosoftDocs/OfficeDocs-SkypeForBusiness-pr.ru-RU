---
title: Teams в среде с Microsoft 365 с поддержкой нескольких геолокационных сред
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
description: В этой статье вы узнаете об использовании Teams в Microsoft 365 с поддержкой нескольких геолокационных сред.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760542"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="d0ddf-103">Teams в Microsoft 365 с поддержкой нескольких геолокации</span><span class="sxs-lookup"><span data-stu-id="d0ddf-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="d0ddf-104">Microsoft Teams — это программное обеспечение для группового чата, центр командной работы в Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="d0ddf-105">Она наряду со службой Microsoft 365 Groups, а SharePoint Online и OneDrive для бизнеса для работы с файлами.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="d0ddf-106">В клиенте OneDrive для бизнеса/SharePoint Online с поддержкой нескольких регионов, где клиент находится во многих географических расположениях, например в Северной Америке, Европе и Австралии, для работы с файлами следует использовать мульти geo-aware, поэтому Teams для совместной работы с файлами также можно использовать несколько регионов.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="d0ddf-107">Эта функциональность является основным средством, которое позволяет Teams поверхностные файлы, которые находятся на нескольких геосхемах.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="d0ddf-108">Это также относится к OneNote и вики-файлам.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="d0ddf-109">Например, на клиенте Contoso с Европой в качестве центрального географического центра и Северной Америке европейский  спутниковый пользователь будет видеть свои файлы OneDrive на вкладке Файлы в левой области, хотя эти файлы находятся в Европе, а США — в центральном расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="d0ddf-110">Кроме того, пользователь может получить доступ к последним использованным файлам в представлении **Последние.**</span><span class="sxs-lookup"><span data-stu-id="d0ddf-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="d0ddf-111">Последние файлы могут включать файлы, общие для пользователей в других регионах.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="d0ddf-112">Кроме того, для SharePoint работы с заданной SharePoint данной группы имеется многоязное географическое внимание.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="d0ddf-113">То есть, если европейский спутниковый пользователь создает команду, соответствующий сайт SharePoint будет создан в Европе.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="d0ddf-114">Файлы, связанные с этой командой, будут храниться в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="d0ddf-115">Все последующие действия, например отправка или редактирование файла, будут храниться в этом европейском расположении, что позволит сохранить данные в этих местах.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="d0ddf-116">Так как мульти geo tenancy — это один глобальный клиент, во время @ упоминаний спутниковые пользователи смогут видеть своих коллег со всего мира, где бы они ни были.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="d0ddf-117">Беседы в чатах, сообщениях каналов, заметки к мгновенным сообщениям и чатых собраний в Teams не являются мульти geo-aware и хранятся только в центральном расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="d0ddf-118">Обычно беседы чата не применяются к потребностям хранения данных.</span><span class="sxs-lookup"><span data-stu-id="d0ddf-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="d0ddf-119">Дополнительные сведения см. в [Microsoft Teams.](location-of-data-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d0ddf-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="d0ddf-120">Поддержка нескольких геосхем для Teams в Microsoft 365 [развития.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)</span><span class="sxs-lookup"><span data-stu-id="d0ddf-120">Multi-Geo support for Teams is on the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783).</span></span>

<span data-ttu-id="d0ddf-121">Дополнительные сведения о multi-Geo можно найти на странице [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="d0ddf-121">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
