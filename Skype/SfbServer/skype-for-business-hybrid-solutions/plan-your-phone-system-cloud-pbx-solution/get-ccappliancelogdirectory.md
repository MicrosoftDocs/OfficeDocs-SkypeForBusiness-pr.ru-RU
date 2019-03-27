---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: d1298454bb347356718fdf24d6761acfea1b71b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890362"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="f539c-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="f539c-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="f539c-104">Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f539c-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="f539c-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f539c-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="f539c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f539c-106">Parameters</span></span>

<span data-ttu-id="f539c-107">Нет</span><span class="sxs-lookup"><span data-stu-id="f539c-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f539c-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="f539c-108">Examples</span></span>
<span data-ttu-id="f539c-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f539c-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="f539c-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="f539c-110">Example 1</span></span>

<span data-ttu-id="f539c-111">В следующем примере показано текущей папки, в котором хранятся журналы для текущего устройства облачных соединителя:</span><span class="sxs-lookup"><span data-stu-id="f539c-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="f539c-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f539c-112">Detailed Description</span></span>
<span data-ttu-id="f539c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f539c-113"></span></span>

<span data-ttu-id="f539c-114">Командлет Get-CcApplianceLogDirectory отображает текущий каталог котором хранятся журналы для соединителя облачных устройства.</span><span class="sxs-lookup"><span data-stu-id="f539c-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="f539c-115">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="f539c-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="f539c-116">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="f539c-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="f539c-117">Примечание. Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="f539c-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f539c-118">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="f539c-118">Input Types</span></span>
<span data-ttu-id="f539c-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f539c-119"></span></span>

<span data-ttu-id="f539c-p102">Нет. Командлет Get-CcApplianceLogDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f539c-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f539c-122">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="f539c-122">Return Types</span></span>
<span data-ttu-id="f539c-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f539c-123"></span></span>

<span data-ttu-id="f539c-124">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="f539c-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f539c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f539c-125">See also</span></span>
<span data-ttu-id="f539c-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f539c-126"></span></span>

[<span data-ttu-id="f539c-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f539c-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

