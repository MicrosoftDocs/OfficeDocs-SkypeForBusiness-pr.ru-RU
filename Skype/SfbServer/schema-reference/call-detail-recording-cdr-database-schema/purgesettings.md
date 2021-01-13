---
title: Таблица PurgeSettings
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'Таблица параметров очистки PurgeSettings содержит сведения, указывающие, следует ли автоматически удалять устаревшие записи регистрации вызовов из базы данных CDR, и когда это следует делать. Обратите внимание, что сведения, относящиеся к убыванию, также можно получить в Skype для бизнеса Server 2015 с помощью следующей команды:'
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823169"
---
# <a name="purgesettings-table"></a><span data-ttu-id="5b6bf-104">Таблица PurgeSettings</span><span class="sxs-lookup"><span data-stu-id="5b6bf-104">PurgeSettings table</span></span>
 
<span data-ttu-id="5b6bf-105">Таблица параметров очистки PurgeSettings содержит сведения, указывающие, следует ли автоматически удалять устаревшие записи регистрации вызовов из базы данных CDR, и когда это следует делать.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="5b6bf-106">Обратите внимание, что сведения, относящиеся к убыванию, также можно получить в Skype для бизнеса Server 2015 с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5b6bf-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="5b6bf-107">Администраторам следует рассматривать таблицу PurgeSettings как только для чтения: изменения параметров очистки подробных вызовов следует вносить только с помощью [new-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) или [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5b6bf-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="5b6bf-108">Эта таблица была представлена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5b6bf-109">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-109">**Column**</span></span>|<span data-ttu-id="5b6bf-110">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-110">**Data Type**</span></span>|<span data-ttu-id="5b6bf-111">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-111">**Key/Index**</span></span>|<span data-ttu-id="5b6bf-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b6bf-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-113">**Id**</span></span> <br/> |<span data-ttu-id="5b6bf-114">int</span><span class="sxs-lookup"><span data-stu-id="5b6bf-114">int</span></span>  <br/> |<span data-ttu-id="5b6bf-115">Primary</span><span class="sxs-lookup"><span data-stu-id="5b6bf-115">Primary</span></span>  <br/> |<span data-ttu-id="5b6bf-116">Уникальный идентификатор для набора параметров очистки CDR.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="5b6bf-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="5b6bf-118">bit</span><span class="sxs-lookup"><span data-stu-id="5b6bf-118">bit</span></span>  <br/> ||<span data-ttu-id="5b6bf-119">Если установлено true (1), Skype для бизнеса Server 2015 будет периодически очищать устаревшие записи из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="5b6bf-120">Очистка будет происходить каждый день во время, установленное с помощью параметра PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="5b6bf-121">Если задано значение False (0), записи не будут очищаться автоматически.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="5b6bf-122">Значение по умолчанию — True.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="5b6bf-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="5b6bf-124">int</span><span class="sxs-lookup"><span data-stu-id="5b6bf-124">int</span></span>  <br/> ||<span data-ttu-id="5b6bf-p104">Задает возраст записей CDR (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-p104">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="5b6bf-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="5b6bf-128">int</span><span class="sxs-lookup"><span data-stu-id="5b6bf-128">int</span></span>  <br/> ||<span data-ttu-id="5b6bf-p105">Задает возраст записей отчета об ошибках (в днях), которые будут удаляться из базы данных: если очистка включена, то все записи отчета об ошибках, возраст которых больше указанного, будут удаляться из базы данных. Значение по умолчанию — 60 дней.</span><span class="sxs-lookup"><span data-stu-id="5b6bf-p105">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="5b6bf-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="5b6bf-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="5b6bf-132">int</span><span class="sxs-lookup"><span data-stu-id="5b6bf-132">int</span></span>  <br/> ||<span data-ttu-id="5b6bf-p106">Задает местное время суток, когда будет выполняться очистка базы данных. Время суток указывается в 24-часовом формате, где 0 соответствует полуночи, а 23 соответствует 11 часам вечера. Обратите внимание, что можно указывать только часы: значение 10 (задающее 10 утра) разрешено, а значение 10:30 (задающее 10:30 утра) не разрешено. Значение по умолчанию - 2 (2:00 ночи).</span><span class="sxs-lookup"><span data-stu-id="5b6bf-p106">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span>  <br/> |
   

