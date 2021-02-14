---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. Все файлы развертывания хранятся в этом каталоге.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800849"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="83044-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="83044-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="83044-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span><span class="sxs-lookup"><span data-stu-id="83044-105">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server.</span></span> <span data-ttu-id="83044-106">Все файлы развертывания хранятся в этом каталоге.</span><span class="sxs-lookup"><span data-stu-id="83044-106">All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="83044-107">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="83044-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="83044-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="83044-108">Parameters</span></span>

<span data-ttu-id="83044-109">Нет</span><span class="sxs-lookup"><span data-stu-id="83044-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="83044-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="83044-110">Examples</span></span>
<span data-ttu-id="83044-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="83044-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="83044-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="83044-112">Example 1</span></span>

<span data-ttu-id="83044-113">В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин компонентов Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="83044-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="83044-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="83044-114">Detailed Description</span></span>
<span data-ttu-id="83044-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="83044-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="83044-116">В Get-CcApplianceDirectory показано, где хранятся все файлы конфигурации и виртуальных машин, журналы и внешние сертификаты для устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="83044-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="83044-117">Каждое устройство Cloud Connector имеет четыре компонента: сервер-посредник, центральное хранилище управления, edge server и контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="83044-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="83044-118">Папка по умолчанию C:\Users \% userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="83044-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="83044-119">Эту папку можно изменить с помощью Set-CCApplianceDirectory управления.</span><span class="sxs-lookup"><span data-stu-id="83044-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="83044-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="83044-120">Input Types</span></span>
<span data-ttu-id="83044-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83044-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="83044-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="83044-122">None.</span></span> <span data-ttu-id="83044-123">Этот Get-CCApplianceDirectory не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="83044-123">The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="83044-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="83044-124">Return Types</span></span>
<span data-ttu-id="83044-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83044-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="83044-126">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="83044-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83044-127">См. также</span><span class="sxs-lookup"><span data-stu-id="83044-127">See also</span></span>
<span data-ttu-id="83044-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83044-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="83044-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="83044-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

