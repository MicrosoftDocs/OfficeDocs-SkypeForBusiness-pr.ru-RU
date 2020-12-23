---
title: Возможности Teams в Службе Microsoft 365 или OneDrive для Office 365 и службе SharePoint Online с несколькими геолокационными группами
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: В этой статье вы узнаете, как использовать Teams в OneDrive или OneDrive для Office 365 и SharePoint Online с поддержкой нескольких геосхем.
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
ms.openlocfilehash: 1fdfd99494b8f65c448a2b1183a183b8cf7477af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583246"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="67779-103">Возможности Teams в Службе Microsoft 365 или OneDrive для Office 365 и службе SharePoint Online с поддержкой нескольких геолокации</span><span class="sxs-lookup"><span data-stu-id="67779-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="67779-104">Microsoft Teams — это групповой чат, центр командной работы в Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="67779-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="67779-105">Она наряду со службой SharePoint Online и OneDrive для бизнеса наряду со службой Microsoft 365 и службой OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="67779-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="67779-106">В клиентах OneDrive для бизнеса и SharePoint Online с несколькими географическими расположениями, такими как Северная Америка, Европа и Австралия, взаимодействие с файлами является многофационным, поэтому совместная работа с файлами в Teams также может быть несколько регионов.</span><span class="sxs-lookup"><span data-stu-id="67779-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="67779-107">Это основная возможность Surface Teams для работы с файлами, которые были на разных геоуровнах.</span><span class="sxs-lookup"><span data-stu-id="67779-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="67779-108">Например, в клиенте Contoso, где Европа расположена как спутниковый геосем, а в Северной Америке — в качестве центрального геоупорядочества, европейский спутниковый пользователь увидит свои файлы OneDrive на вкладке "Файлы" в левой области, хотя они находятся в Европе, а сша — в качестве центрального расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="67779-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="67779-109">Кроме того, пользователь может получить доступ к файлам, которые использовались последними, в области "Последние".</span><span class="sxs-lookup"><span data-stu-id="67779-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="67779-110">Последние файлы могут включать файлы, общий доступ к ним от пользователей из других геосхем, а также могут быть освоеными в других геолокации, на которые распространяется действие клиента.</span><span class="sxs-lookup"><span data-stu-id="67779-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="67779-111">Сайт группы группы также может быть не только геосканным, но и несколькими.</span><span class="sxs-lookup"><span data-stu-id="67779-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="67779-112">То есть, если европейский спутниковый пользователь создает группу, соответствующий сайт групп будет создан в Европе, а файлы, связанные с этой группой, будут храниться в этом месте.</span><span class="sxs-lookup"><span data-stu-id="67779-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="67779-113">Все последующие действия, такие как отправка или редактирование файла, будут нацелены на это расположение в Европе, но при этом будут сохраняться обещания о размещении данных для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="67779-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="67779-114">Это возможно с помощью того, что группы Microsoft 365 становятся частью данной службы с несколькими геос учетом.</span><span class="sxs-lookup"><span data-stu-id="67779-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="67779-115">Так как мультисхемические клиенты — это один глобальный клиент, во время @упоминаний спутниковые пользователи смогут видеть своих коллег со всего мира, где бы они ни были.</span><span class="sxs-lookup"><span data-stu-id="67779-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="67779-116">Обратите внимание на то, что беседы в чатах и заметки о мгновенных сообщениях в Teams не могут быть частью с несколькими местоположениями и хранятся только в центральном расположении клиента.</span><span class="sxs-lookup"><span data-stu-id="67779-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="67779-117">Как правило, беседы чата не применяются к потребностям места проживания данных.</span><span class="sxs-lookup"><span data-stu-id="67779-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="67779-118">Дополнительные сведения о multi-Geo можно найти на странице [microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="67779-118">For more information about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>