---
title: Таблица PurgeSettings (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'В таблице PurgeSettings содержатся сведения о том, должны ли устаревшие записи автоматически удаляться из базы данных качества обслуживания, и когда это должно происходить. Обратите внимание, что сведения, относящиеся к убыванию, также можно получить из командной оболочки Skype для бизнеса Server, выдав следующую команду:'
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815809"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="2684b-104">Таблица PurgeSettings (QoE)</span><span class="sxs-lookup"><span data-stu-id="2684b-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="2684b-105">В таблице PurgeSettings содержатся сведения о том, должны ли устаревшие записи автоматически удаляться из базы данных качества обслуживания, и когда это должно происходить.</span><span class="sxs-lookup"><span data-stu-id="2684b-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="2684b-106">Обратите внимание, что сведения, относящиеся к убыванию, также можно получить из командной оболочки Skype для бизнеса Server с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="2684b-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="2684b-107">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2684b-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2684b-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2684b-108">**Column**</span></span>|<span data-ttu-id="2684b-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="2684b-109">**Data Type**</span></span>|<span data-ttu-id="2684b-110">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="2684b-110">**Key/Index**</span></span>|<span data-ttu-id="2684b-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="2684b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2684b-112">**ИД**</span><span class="sxs-lookup"><span data-stu-id="2684b-112">**ID**</span></span> <br/> |<span data-ttu-id="2684b-113">int</span><span class="sxs-lookup"><span data-stu-id="2684b-113">int</span></span>  <br/> |<span data-ttu-id="2684b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="2684b-114">Primary</span></span>  <br/> |<span data-ttu-id="2684b-115">Уникальный идентификатор набора параметров, связанных с очисткой записей качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2684b-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="2684b-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="2684b-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="2684b-117">bit</span><span class="sxs-lookup"><span data-stu-id="2684b-117">bit</span></span>  <br/> ||<span data-ttu-id="2684b-118">Если установлено true (1), Microsoft Lync Server 2013 будет периодически очищать устаревшие записи из базы данных QoE.</span><span class="sxs-lookup"><span data-stu-id="2684b-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="2684b-119">Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="2684b-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="2684b-120">Если задано значение False (0), записи не будут очищаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="2684b-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="2684b-121">Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="2684b-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="2684b-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="2684b-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="2684b-123">int</span><span class="sxs-lookup"><span data-stu-id="2684b-123">int</span></span>  <br/> ||<span data-ttu-id="2684b-p104">Определяет возраст записей качества обслуживания (в днях), которые должны очищаться. Если очистка включена, записи старше этого значения будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="2684b-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="2684b-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="2684b-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="2684b-127">int</span><span class="sxs-lookup"><span data-stu-id="2684b-127">int</span></span>  <br/> ||<span data-ttu-id="2684b-p105">Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 означает полночь, а 23 означает 11 часов вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи). Определяет время суток (по местному времени), когда должна выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11:00 вечера. Обратите внимание на то, что вы можете указать только час: значение 10 (соответствующее 10:00 утра) допускается, а значение 10:30 или 10.5 (соответствующее 10:30 утра) — нет. Значение по умолчанию — 1 (1:00 ночи).</span><span class="sxs-lookup"><span data-stu-id="2684b-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

