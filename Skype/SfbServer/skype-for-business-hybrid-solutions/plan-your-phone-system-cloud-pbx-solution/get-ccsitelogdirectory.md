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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: a03c4c0cc3e993fb5e1426f3f27f76a68d081c26
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003359"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="c57af-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="c57af-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="c57af-104">Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c57af-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="c57af-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c57af-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="c57af-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c57af-106">Parameters</span></span>

<span data-ttu-id="c57af-107">Нет</span><span class="sxs-lookup"><span data-stu-id="c57af-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="c57af-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="c57af-108">Examples</span></span>
<span data-ttu-id="c57af-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c57af-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="c57af-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c57af-110">Example 1</span></span>

<span data-ttu-id="c57af-111">В следующем примере показана текущая папка, в которой хранятся файлы журнала для сайта облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="c57af-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="c57af-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c57af-112">Detailed Description</span></span>
<span data-ttu-id="c57af-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c57af-113"></span></span>

<span data-ttu-id="c57af-114">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут\логс.</span><span class="sxs-lookup"><span data-stu-id="c57af-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="c57af-115">Чтобы изменить эту папку, выполните командлет Set-CcSiteDirectory.</span><span class="sxs-lookup"><span data-stu-id="c57af-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="c57af-116">Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="c57af-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="c57af-117">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c57af-117">Input Types</span></span>
<span data-ttu-id="c57af-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c57af-118"></span></span>

<span data-ttu-id="c57af-p102">Нет. Командлет Get-CcSiteLogDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c57af-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c57af-121">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c57af-121">Return Types</span></span>
<span data-ttu-id="c57af-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c57af-122"></span></span>

<span data-ttu-id="c57af-123">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="c57af-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c57af-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c57af-124">See also</span></span>
<span data-ttu-id="c57af-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c57af-125"></span></span>

[<span data-ttu-id="c57af-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="c57af-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

