---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800829"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="9f52e-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="9f52e-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="9f52e-104">Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="9f52e-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="9f52e-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9f52e-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="9f52e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f52e-106">Parameters</span></span>

<span data-ttu-id="9f52e-107">Нет</span><span class="sxs-lookup"><span data-stu-id="9f52e-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9f52e-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f52e-108">Examples</span></span>
<span data-ttu-id="9f52e-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52e-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9f52e-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9f52e-110">Example 1</span></span>

<span data-ttu-id="9f52e-111">В следующем примере показана текущая папка, в которой хранятся журналы для текущего устройства в облачном соединителе:</span><span class="sxs-lookup"><span data-stu-id="9f52e-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="9f52e-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9f52e-112">Detailed Description</span></span>
<span data-ttu-id="9f52e-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52e-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9f52e-114">Командлет Get-Ккапплианцелогдиректори показывает текущий каталог, в котором хранятся журналы для устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="9f52e-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="9f52e-115">По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\апплианцерут\логс.</span><span class="sxs-lookup"><span data-stu-id="9f52e-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="9f52e-116">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="9f52e-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="9f52e-117">Примечание. Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="9f52e-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9f52e-118">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9f52e-118">Input Types</span></span>
<span data-ttu-id="9f52e-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52e-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9f52e-p102">Нет. Командлет Get-CcApplianceLogDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9f52e-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9f52e-122">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9f52e-122">Return Types</span></span>
<span data-ttu-id="9f52e-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52e-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9f52e-124">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="9f52e-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f52e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9f52e-125">See also</span></span>
<span data-ttu-id="9f52e-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52e-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9f52e-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="9f52e-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

