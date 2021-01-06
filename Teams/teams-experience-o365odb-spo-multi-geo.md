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
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757754"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="3db78-103">Возможности Teams в многоязной области Microsoft 365 с поддержкой нескольких геолокации</span><span class="sxs-lookup"><span data-stu-id="3db78-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="3db78-104">Microsoft Teams — это групповой чат, центр командной работы в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3db78-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="3db78-105">Она наряду со службой SharePoint и OneDrive, а также службой Групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3db78-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="3db78-106">В организации с несколькими регионами, в которой клиент расширяется до различных географических регионов, таких как Северная Америка, Европа и Австралия, для работы с файлами в ней следует использовать мульти geo aware, поэтому взаимодействие Teams с файлами также можно использовать в разных регионах.</span><span class="sxs-lookup"><span data-stu-id="3db78-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="3db78-107">Это позволяет Teams использовать для работы с файлами, которые были в разных регионах.</span><span class="sxs-lookup"><span data-stu-id="3db78-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="3db78-108">Например, в клиенте Contoso, где Европа расположена как спутниковый геосем, а в Северной Америке — в качестве центрального геоупорядочества, европейский спутниковый пользователь увидит свои файлы OneDrive на вкладке "Файлы" в левой области, хотя они находятся в Европе, а сша — в качестве центрального расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="3db78-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="3db78-109">Кроме того, пользователь может получить доступ к файлам, которые использовались последними, в области "Последние".</span><span class="sxs-lookup"><span data-stu-id="3db78-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="3db78-110">Последние файлы могут включать файлы, общий доступ к ним от пользователей из других геолокации.</span><span class="sxs-lookup"><span data-stu-id="3db78-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="3db78-111">Сайт SharePoint группы также может быть частью с несколькими геос учетом.</span><span class="sxs-lookup"><span data-stu-id="3db78-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="3db78-112">То есть, если европейский спутниковый пользователь создает команду, соответствующий сайт SharePoint будет создан в Европе, а файлы, связанные с этой командой, будут храниться в этом месте.</span><span class="sxs-lookup"><span data-stu-id="3db78-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="3db78-113">Все последующие действия, такие как отправка или редактирование файла, будут храниться в европейском расположении, сохраняя обещания о размещении данных для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="3db78-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="3db78-114">Обратите внимание на то, что беседы в чатах и заметки о мгновенных сообщениях в Teams не могут быть частью с несколькими географическими расположениями и хранятся только в центральном расположении организации.</span><span class="sxs-lookup"><span data-stu-id="3db78-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="3db78-115">Дополнительные сведения о мультисхеговных возможностях см. в [службе Microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)</span><span class="sxs-lookup"><span data-stu-id="3db78-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
