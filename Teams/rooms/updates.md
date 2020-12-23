---
title: Управление обновлениями Windows для комнат Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Администратор может узнать, как управлять Обновлениями Windows и обновлениями функций Windows для комнат Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e52c1fdf3bb35be6869320aa57e6f5aff5fd0773
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905311"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="27c8d-103">Управление обновлениями Windows</span><span class="sxs-lookup"><span data-stu-id="27c8d-103">Manage Windows Updates</span></span>

<span data-ttu-id="27c8d-104">Комнаты Microsoft Teams работают на windows 10 Enterprise IoT или Windows 10 Enterprise (VL) и получают те же сборки Windows и ОС, что и стандартные настольные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="27c8d-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="27c8d-105">Обновлением Windows можно управлять, как рассмотрено в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="27c8d-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="27c8d-106">Практический подход</span><span class="sxs-lookup"><span data-stu-id="27c8d-106">Hands-off approach</span></span> 

- <span data-ttu-id="27c8d-107">По умолчанию обновления загружаются автоматически из Обновлений Windows и устанавливаются в нечасовом режиме.</span><span class="sxs-lookup"><span data-stu-id="27c8d-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="27c8d-108">Обновления, не отложенные, устанавливаются автоматически в первый день выпуска.</span><span class="sxs-lookup"><span data-stu-id="27c8d-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="27c8d-109">Обновления качества и драйверы загружаются и устанавливаются автоматически каждый день.</span><span class="sxs-lookup"><span data-stu-id="27c8d-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="27c8d-110">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="27c8d-110">Feature Updates.</span></span> <span data-ttu-id="27c8d-111">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="27c8d-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="27c8d-112">Обновления Windows для бизнеса (GPO или Intune)</span><span class="sxs-lookup"><span data-stu-id="27c8d-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="27c8d-113">[Скачивание Обновлений Windows для](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) бизнеса</span><span class="sxs-lookup"><span data-stu-id="27c8d-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="27c8d-114">Обновления загружаются из Windows Update или WSUS, но с настроенными задержками после даты первоначального выпуска.</span><span class="sxs-lookup"><span data-stu-id="27c8d-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="27c8d-115">Вы можете использовать несколько OUS или отфильтрованных политик для создания кругов развертывания, где администраторы могут указать, какие устройства сначала устанавливают обновления качества, а какие — устанавливать позднее.</span><span class="sxs-lookup"><span data-stu-id="27c8d-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="27c8d-116">Надежность и производительность можно протестировать на подмножество систем перед развертыванием обновлений во всем развертывании без накладных расходов на управление Обновлениями Windows в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="27c8d-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="27c8d-117">WSUS и Windows Updates [](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) для бизнеса можно настроить одновременно, если вы хотите управлять пропускной способностью и управлением Обновлениями Windows для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="27c8d-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="27c8d-118">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="27c8d-118">Feature updates.</span></span> <span data-ttu-id="27c8d-119">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="27c8d-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="27c8d-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="27c8d-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="27c8d-121">[Скачивание WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="27c8d-121">[WSUS/Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="27c8d-122">Он похож на Windows Update для бизнеса, но с возможностью дополнительного выбора целевой аудитории для конкретного КБ в каждом "круге" или во всем развертывании.</span><span class="sxs-lookup"><span data-stu-id="27c8d-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="27c8d-123">Каждое обновление можно развертывать и тестировать по отдельности, а не рассчитывать только на задержку.</span><span class="sxs-lookup"><span data-stu-id="27c8d-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="27c8d-124">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="27c8d-124">Feature updates.</span></span> <span data-ttu-id="27c8d-125">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="27c8d-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="27c8d-126">Обновления функций</span><span class="sxs-lookup"><span data-stu-id="27c8d-126">Feature updates</span></span>

<span data-ttu-id="27c8d-127">В отличие от обновлений качества и без отложенного обновления, обновления функций (основные выпуски ОС) Windows 10 будут устанавливаться только после тестирования корпорацией Майкрософт и проверки функциональности обновлений с помощью комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="27c8d-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="27c8d-128">Даже если обновление выпущено для Semi-Annual Channel (или targeted, если в системах настроен этот канал для тестирования) или было разопрошено вручную, устройство Microsoft Room Systems не позволит установить неотвеченное обновление.</span><span class="sxs-lookup"><span data-stu-id="27c8d-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="27c8d-129">Комнаты Microsoft Teams работают "за компьютером" с практическим подходом и не устанавливают Обновление Windows или не перезагружают устройство автоматически для Обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="27c8d-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="27c8d-130">Системы скачивает обновление и ждет следующей перезагрузки, чтобы установить его.</span><span class="sxs-lookup"><span data-stu-id="27c8d-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="27c8d-131">Если кто-то не перезагрузает его вручную, установка происходит только при автоматической ночной перезагрузке.</span><span class="sxs-lookup"><span data-stu-id="27c8d-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="27c8d-132">Обновления Windows должны быть прозрачными в помещении, а обычная работа не должна быть прервана Обновлениями Windows.</span><span class="sxs-lookup"><span data-stu-id="27c8d-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="27c8d-133">Если вы решите объединить устройства с доменом, используйте Microsoft Endpoint Configuration Manager или WSUS.</span><span class="sxs-lookup"><span data-stu-id="27c8d-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="27c8d-134">Уделяем особое внимание политикам или действиям, которые при этом могут привести к обновлению устройства или принудительной перезагрузке в часы.</span><span class="sxs-lookup"><span data-stu-id="27c8d-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="27c8d-135">Системы в развертывании не должны перезагружаться во время использования или оповещений об обновлениях Windows через пользовательский интерфейс в часы использования. В этом случае рассмотрите конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="27c8d-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>