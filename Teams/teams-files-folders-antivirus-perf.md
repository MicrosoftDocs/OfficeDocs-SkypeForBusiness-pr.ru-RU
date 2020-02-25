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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1519038cb2393687a031e9b2c1ea828f999728
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265624"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="820d0-103">Файлы и папки Teams, которые должны быть исключены из проверки на вирусы</span><span class="sxs-lookup"><span data-stu-id="820d0-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="820d0-104">Вы можете повысить общую производительность развертывания Teams, запретив антивирусным программам проверять определенные файлы и папки в группах.</span><span class="sxs-lookup"><span data-stu-id="820d0-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="820d0-105">Это позволит избежать расхода системных ресурсов на просмотр файлов и папок, которые не требуется сканировать.</span><span class="sxs-lookup"><span data-stu-id="820d0-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="820d0-106">Когда пользователи загружают файлы или совместно с другими файлами, эти файлы не проходят через расположения, указанные в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="820d0-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="820d0-107">Антивирусная программа будет регулярно сканировать файлы, в которых ваши пользователи выполняют передачу, скачивание или предоставление общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="820d0-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="820d0-108">Файлы и папки, которые нужно добавить в список надежных антивирусных программ</span><span class="sxs-lookup"><span data-stu-id="820d0-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="820d0-109">С помощью процедур, поддерживаемых антивирусной программой, добавьте в списки надежных файлов указанные ниже файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="820d0-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="820d0-110">Это обеспечит экономию системных ресурсов, устраняя антивирусные проверки этих местоположений.</span><span class="sxs-lookup"><span data-stu-id="820d0-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="820d0-111">Приложениях</span><span class="sxs-lookup"><span data-stu-id="820d0-111">Programs</span></span>

<span data-ttu-id="820d0-112">Добавьте следующие программы Teams в список надежных для антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="820d0-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="820d0-113">**%локалаппдата%\микрософт\теамс\куррент\теамс.ексе**</span><span class="sxs-lookup"><span data-stu-id="820d0-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="820d0-114">**%локалаппдата%\микрософт\теамс\упдате.ексе**</span><span class="sxs-lookup"><span data-stu-id="820d0-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="820d0-115">Папки</span><span class="sxs-lookup"><span data-stu-id="820d0-115">Folders</span></span>

<span data-ttu-id="820d0-116">Добавьте следующие папки Teams в список надежных для антивирусных программ.</span><span class="sxs-lookup"><span data-stu-id="820d0-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="820d0-117">Категория</span><span class="sxs-lookup"><span data-stu-id="820d0-117">Category</span></span>  |<span data-ttu-id="820d0-118">Местоположение</span><span class="sxs-lookup"><span data-stu-id="820d0-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="820d0-119">Файлы программы</span><span class="sxs-lookup"><span data-stu-id="820d0-119">Program files</span></span>  |<span data-ttu-id="820d0-120">%локалаппдата%\микрософт\теамс</span><span class="sxs-lookup"><span data-stu-id="820d0-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="820d0-121">Файлы данных</span><span class="sxs-lookup"><span data-stu-id="820d0-121">Data files</span></span>     |<span data-ttu-id="820d0-122">%аппдата%\микрософт\теамс</span><span class="sxs-lookup"><span data-stu-id="820d0-122">%appdata%\Microsoft\Teams</span></span>\ |
