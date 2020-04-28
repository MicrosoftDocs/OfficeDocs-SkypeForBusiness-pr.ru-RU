---
title: Взаимодействие Teams в Microsoft 365 или Office 365 с поддержкой OneDrive и SharePoint Online с несколькими геогеографическими возможностями
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: В этой статье вы узнаете об использовании Teams в Microsoft 365 или Office 365 с несколькими геодоменными средствами с поддержкой OneDrive и SharePoint Online.
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
ms.openlocfilehash: 4e754177de6f08476c9160254f2334f6f3ac18d3
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903144"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="9aa33-103">Взаимодействие Teams в Microsoft 365 или Office 365 с поддержкой OneDrive и SharePoint Online с несколькими геогеографическими возможностями</span><span class="sxs-lookup"><span data-stu-id="9aa33-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="9aa33-104">Microsoft Teams — это программное обеспечение для группового чата, центр совместной работы в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9aa33-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="9aa33-105">На нем установлена служба Microsoft 365 Groups, а также SharePoint Online и OneDrive для бизнеса для работы с файлами.</span><span class="sxs-lookup"><span data-stu-id="9aa33-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="9aa33-106">В хранилище OneDrive для бизнеса или SharePoint Online с несколькими геогеографическими положениями, в которых клиент расширяется для многих географических регионов, например в Северной Америке, Европе и Австралии, для работы с файлами в разных географических регионах может быть задано приложение для совместной работы с несколькими географических учетными данными.</span><span class="sxs-lookup"><span data-stu-id="9aa33-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="9aa33-107">Это ключевая возможность для Teams для размещения файлов, размещенных в нескольких Geosах, в собственной работе с файлами.</span><span class="sxs-lookup"><span data-stu-id="9aa33-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="9aa33-108">Например, в компании Contoso в качестве вспомогательной географической и Северной Америки в качестве центрального географической и копризнанной (в левой области) пользователи, которые размещаются в странах Европы, будут видеть свои файлы OneDrive, но они хранятся в местоположении данных в Европе и США — центральное расположение клиента.</span><span class="sxs-lookup"><span data-stu-id="9aa33-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="9aa33-109">Кроме того, пользователь может получить доступ к последним файлам в колонке "Недавние представления".</span><span class="sxs-lookup"><span data-stu-id="9aa33-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="9aa33-110">Последние файлы могут содержать файлы, к которым предоставлен общий доступ пользователям, в других GEOS, и они могут быть включены в другие геогеографически расположений, в которых развернут клиент.</span><span class="sxs-lookup"><span data-stu-id="9aa33-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="9aa33-111">На сайте группы данной группы также есть возможность учитывать несколько географических параметров.</span><span class="sxs-lookup"><span data-stu-id="9aa33-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="9aa33-112">Таким образом, если пользователь европейской спутниковой связи создает группу, сайт соответствующих групп будет создан в странах Европы, и файлы, связанные с этой группой, будут храниться в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="9aa33-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="9aa33-113">Все последующие возможности, такие как отправка нового файла или редактирование файла, будут нацелены на это странное расположение, учитывая, что Кель данных для этих файлов.</span><span class="sxs-lookup"><span data-stu-id="9aa33-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="9aa33-114">Это все, что можно сделать с помощью базовой основы для групп Microsoft 365, в которой установлено несколько географических интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="9aa33-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="9aa33-115">Поскольку многогеографический клиентский период является единым глобальным клиентом, во время @ упоминаний сопутствующих пользователей пользователи могут видеть своих коллег из любого земного шара, независимо от того, где они находятся.</span><span class="sxs-lookup"><span data-stu-id="9aa33-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="9aa33-116">Обратите внимание, что беседы в чате и заметки о мгновенных сообщениях в службе Teams не поддерживаются в разных географических целях, и все они хранятся только внутри центрального расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="9aa33-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="9aa33-117">Как правило, беседы в чате не применяются к кельам данных.</span><span class="sxs-lookup"><span data-stu-id="9aa33-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="9aa33-118">Дополнительные сведения о Office 365 Multi-Geo можно найти на [странице Microsoft Multi-географических возможностей](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="9aa33-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>