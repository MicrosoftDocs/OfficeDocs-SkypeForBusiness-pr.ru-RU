---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: The Get-CcSiteLogDirectory shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.
ms.openlocfilehash: cace3ce3757294adbb3c55db24c619925f55ce5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799889"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="9432b-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="9432b-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="9432b-104">The Get-CcSiteLogDirectory shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span><span class="sxs-lookup"><span data-stu-id="9432b-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="9432b-105">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9432b-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="9432b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9432b-106">Parameters</span></span>

<span data-ttu-id="9432b-107">Нет</span><span class="sxs-lookup"><span data-stu-id="9432b-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9432b-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="9432b-108">Examples</span></span>
<span data-ttu-id="9432b-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9432b-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9432b-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9432b-110">Example 1</span></span>

<span data-ttu-id="9432b-111">В следующем примере показана текущая папка, в которой хранятся файлы журнала для сайта Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9432b-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="9432b-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9432b-112">Detailed Description</span></span>
<span data-ttu-id="9432b-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9432b-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9432b-114">Папка по умолчанию C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="9432b-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="9432b-115">Вы можете изменить папку, задав Set-CcSiteDirectory управления.</span><span class="sxs-lookup"><span data-stu-id="9432b-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="9432b-116">Не существует отдельного cmdlet, который изменяет только расположение папки журнала без изменения каталога сайта.</span><span class="sxs-lookup"><span data-stu-id="9432b-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9432b-117">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9432b-117">Input Types</span></span>
<span data-ttu-id="9432b-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9432b-118"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9432b-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="9432b-119">None.</span></span> <span data-ttu-id="9432b-120">Этот Get-CcSiteLogDirectory не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="9432b-120">The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9432b-121">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9432b-121">Return Types</span></span>
<span data-ttu-id="9432b-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9432b-122"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9432b-123">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="9432b-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9432b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9432b-124">See also</span></span>
<span data-ttu-id="9432b-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9432b-125"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9432b-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="9432b-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

