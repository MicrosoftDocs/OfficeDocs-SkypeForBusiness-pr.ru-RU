---
title: Get-CcApplianceLogDirectory
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
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="a6285-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="a6285-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="a6285-104">Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a6285-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="a6285-105">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a6285-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="a6285-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6285-106">Parameters</span></span>

<span data-ttu-id="a6285-107">Нет</span><span class="sxs-lookup"><span data-stu-id="a6285-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a6285-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="a6285-108">Examples</span></span>
<span data-ttu-id="a6285-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a6285-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="a6285-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a6285-110">Example 1</span></span>

<span data-ttu-id="a6285-111">В следующем примере показано текущей папки, в котором хранятся журналы для текущего устройства облачных соединителя:</span><span class="sxs-lookup"><span data-stu-id="a6285-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a6285-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a6285-112">Detailed Description</span></span>
<span data-ttu-id="a6285-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a6285-113"></span></span>

<span data-ttu-id="a6285-114">Командлет Get-CcApplianceLogDirectory отображает текущий каталог котором хранятся журналы для соединителя облачных устройства.</span><span class="sxs-lookup"><span data-stu-id="a6285-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="a6285-115">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="a6285-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="a6285-116">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="a6285-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="a6285-117">Примечание. Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="a6285-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a6285-118">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a6285-118">Input Types</span></span>
<span data-ttu-id="a6285-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6285-119"></span></span>

<span data-ttu-id="a6285-p102">Нет. Командлет Get-CcApplianceLogDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a6285-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a6285-122">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a6285-122">Return Types</span></span>
<span data-ttu-id="a6285-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6285-123"></span></span>

<span data-ttu-id="a6285-124">Эта команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="a6285-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6285-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a6285-125">See also</span></span>
<span data-ttu-id="a6285-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6285-126"></span></span>

[<span data-ttu-id="a6285-127">SET-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a6285-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

