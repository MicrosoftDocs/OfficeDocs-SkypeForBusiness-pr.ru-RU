---
title: Управление Windows обновлениями для Комнаты Microsoft Teams
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
description: Администратор может узнать, как управлять обновлениями Windows обновлениями Windows обновлениями функций для Комнаты Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117367"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="7c313-103">Управление Windows обновлениями</span><span class="sxs-lookup"><span data-stu-id="7c313-103">Manage Windows Updates</span></span>

<span data-ttu-id="7c313-104">Комнаты Microsoft Teams работает на Windows 10 Корпоративная IoT или Windows 10 Корпоративная (VL) и получает те же сборки Windows Updates и OS, что и стандартный настольный компьютер.</span><span class="sxs-lookup"><span data-stu-id="7c313-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="7c313-105">Windows Управление обновлениями можно управлять, как рассмотрено в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7c313-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="7c313-106">Практический подход</span><span class="sxs-lookup"><span data-stu-id="7c313-106">Hands-off approach</span></span> 

- <span data-ttu-id="7c313-107">По умолчанию обновления загружаются непосредственно из Windows обновления и устанавливаются в не часы.</span><span class="sxs-lookup"><span data-stu-id="7c313-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="7c313-108">Обновления, не отложенные, устанавливаются автоматически с первого дня выпуска.</span><span class="sxs-lookup"><span data-stu-id="7c313-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="7c313-109">Обновления качества и драйверы автоматически загружаются и устанавливаются с первого дня.</span><span class="sxs-lookup"><span data-stu-id="7c313-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="7c313-110">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="7c313-110">Feature Updates.</span></span> <span data-ttu-id="7c313-111">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="7c313-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="7c313-112">Windows Обновления для бизнеса (GPO или Intune)</span><span class="sxs-lookup"><span data-stu-id="7c313-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="7c313-113">[Windows обновления для](/windows/deployment/update/waas-manage-updates-wufb) бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c313-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="7c313-114">Обновления загружаются с Windows Update или WSUS, но с настроенными задержками, которые были просуммированы до исходной даты выпуска.</span><span class="sxs-lookup"><span data-stu-id="7c313-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="7c313-115">Вы можете использовать несколько OUs или отфильтрованную политику для создания "колец" развертывания, где администраторы могут указать, какие устройства сначала устанавливают обновления качества, а какие — позднее.</span><span class="sxs-lookup"><span data-stu-id="7c313-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="7c313-116">Надежность и производительность можно протестировать на подмножество систем перед развертыванием обновлений во всем развертывании без накладной Windows обновлений в Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="7c313-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="7c313-117">Обновления WSUS и Windows для бизнеса [](/windows/deployment/update/waas-integrate-wufb) можно настроить одновременно, если вы хотите управлять пропускной способностью и управлять Windows обновлениями для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7c313-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="7c313-118">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="7c313-118">Feature updates.</span></span> <span data-ttu-id="7c313-119">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="7c313-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="7c313-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="7c313-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="7c313-121">[Загрузка WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="7c313-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="7c313-122">Как Windows обновление для бизнеса, но с дополнительным вариантом выбора целевой аудитории для каждого "звонка" или всего развертывания.</span><span class="sxs-lookup"><span data-stu-id="7c313-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="7c313-123">Каждое обновление можно развертывать и тестировать по отдельности, а не с задержкой.</span><span class="sxs-lookup"><span data-stu-id="7c313-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="7c313-124">Обновления функций.</span><span class="sxs-lookup"><span data-stu-id="7c313-124">Feature updates.</span></span> <span data-ttu-id="7c313-125">См. примечания, которые следуют за ними.</span><span class="sxs-lookup"><span data-stu-id="7c313-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="7c313-126">Обновления функций</span><span class="sxs-lookup"><span data-stu-id="7c313-126">Feature updates</span></span>

<span data-ttu-id="7c313-127">В отличие от обновлений, не вносях в отложенное обновление, Windows 10 обновления функций (основные выпуски ОС) будут устанавливаться только после тестирования и проверки функциональности обновлений с Комнаты Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7c313-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="7c313-128">Даже если обновление выпущено на канале Semi-Annual Channel (или Targeted, если в системе установлен этот канал для тестирования) или было отгрузчено вручную, устройство Microsoft Room Systems не позволит установить нетестируемое обновление.</span><span class="sxs-lookup"><span data-stu-id="7c313-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="7c313-129">Комнаты Microsoft Teams функции "готовы" к практическим функциям и не устанавливаются автоматически Windows обновления или перезагрузки устройства для Windows обновления.</span><span class="sxs-lookup"><span data-stu-id="7c313-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="7c313-130">Системы загрузят обновление и подождите следующей перезагрузки, чтобы установить его.</span><span class="sxs-lookup"><span data-stu-id="7c313-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="7c313-131">Если кто-то не перезагрузает его вручную, установка происходит только при автоматической ночной перезагрузке.</span><span class="sxs-lookup"><span data-stu-id="7c313-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="7c313-132">Windows Обновления должны быть прозрачными в помещении, и обычные операции не должны Windows обновлениями.</span><span class="sxs-lookup"><span data-stu-id="7c313-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="7c313-133">Если вы решите присоединиться к домену устройства, используйте Microsoft Endpoint Configuration Manager или WSUS.</span><span class="sxs-lookup"><span data-stu-id="7c313-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="7c313-134">Уделяем особое внимание политикам или действиям, которые при этом приводит к обновлению устройства или принудительной перезагрузке в часы работы.</span><span class="sxs-lookup"><span data-stu-id="7c313-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="7c313-135">Системы в развертывании не должны перезагружаться во время использования или оповещения о Windows обновления над пользовательским интерфейсом в часы использования, просмотрите конфигурацию в этом случае.</span><span class="sxs-lookup"><span data-stu-id="7c313-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>