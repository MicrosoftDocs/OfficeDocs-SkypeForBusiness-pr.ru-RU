---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: c4354920ac25d076e550c5eda3a641eef0c8b900
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886129"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="37bd0-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="37bd0-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="37bd0-104">Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="37bd0-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="37bd0-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="37bd0-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="37bd0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="37bd0-106">Parameters</span></span>

<span data-ttu-id="37bd0-107">Нет</span><span class="sxs-lookup"><span data-stu-id="37bd0-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="37bd0-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="37bd0-108">Examples</span></span>
<span data-ttu-id="37bd0-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="37bd0-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="37bd0-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="37bd0-110">Example 1</span></span>

<span data-ttu-id="37bd0-111">В следующем примере показано текущей папки, где хранятся файлы журнала для соединителя облака сайта:</span><span class="sxs-lookup"><span data-stu-id="37bd0-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="37bd0-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="37bd0-112">Detailed Description</span></span>
<span data-ttu-id="37bd0-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="37bd0-113"></span></span>

<span data-ttu-id="37bd0-114">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="37bd0-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="37bd0-115">Чтобы изменить эту папку, выполните командлет Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="37bd0-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="37bd0-116">Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="37bd0-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="37bd0-117">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="37bd0-117">Input Types</span></span>
<span data-ttu-id="37bd0-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="37bd0-118"></span></span>

<span data-ttu-id="37bd0-p102">Нет. Командлет Get-CcSiteLogDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="37bd0-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="37bd0-121">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="37bd0-121">Return Types</span></span>
<span data-ttu-id="37bd0-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="37bd0-122"></span></span>

<span data-ttu-id="37bd0-123">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="37bd0-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="37bd0-124">См. также</span><span class="sxs-lookup"><span data-stu-id="37bd0-124">See also</span></span>
<span data-ttu-id="37bd0-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="37bd0-125"></span></span>

[<span data-ttu-id="37bd0-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="37bd0-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

