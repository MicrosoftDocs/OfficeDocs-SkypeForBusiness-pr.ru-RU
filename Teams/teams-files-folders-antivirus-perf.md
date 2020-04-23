---
title: Файлы и папки Teams, которые должны быть исключены из проверки на вирусы
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Улучшите производительность Teams за счет исключения некоторых файлов и папок из обычной проверки антивирусной программы.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579595"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="5cd00-103">Файлы и папки Teams, которые должны быть исключены из проверки на вирусы</span><span class="sxs-lookup"><span data-stu-id="5cd00-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="5cd00-104">Вы можете повысить общую производительность развертывания Teams, запретив антивирусным программам проверять определенные файлы и папки в группах.</span><span class="sxs-lookup"><span data-stu-id="5cd00-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="5cd00-105">Это позволит избежать расхода системных ресурсов на просмотр файлов и папок, которые не требуется сканировать.</span><span class="sxs-lookup"><span data-stu-id="5cd00-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="5cd00-106">Когда пользователи загружают файлы или совместно с другими файлами, эти файлы не проходят через расположения, указанные в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="5cd00-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="5cd00-107">Антивирусная программа будет регулярно сканировать файлы, в которых ваши пользователи выполняют передачу, скачивание или предоставление общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="5cd00-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="5cd00-108">Файлы и папки, которые нужно добавить в список надежных антивирусных программ</span><span class="sxs-lookup"><span data-stu-id="5cd00-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="5cd00-109">С помощью процедур, поддерживаемых антивирусной программой, добавьте в списки надежных файлов указанные ниже файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="5cd00-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="5cd00-110">Это обеспечит экономию системных ресурсов, устраняя антивирусные проверки этих местоположений.</span><span class="sxs-lookup"><span data-stu-id="5cd00-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="5cd00-111">Приложениях</span><span class="sxs-lookup"><span data-stu-id="5cd00-111">Programs</span></span>

<span data-ttu-id="5cd00-112">Добавьте следующие программы Teams в список надежных для антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="5cd00-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="5cd00-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="5cd00-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="5cd00-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="5cd00-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

