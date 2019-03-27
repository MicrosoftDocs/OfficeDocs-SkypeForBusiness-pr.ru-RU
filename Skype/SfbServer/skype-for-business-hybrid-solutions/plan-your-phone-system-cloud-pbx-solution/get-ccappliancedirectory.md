---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  '
ms.openlocfilehash: bcd80018b2286865945638f66c13e4c5198346dc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891485"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="4e6e9-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4e6e9-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="4e6e9-p102">Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  </span><span class="sxs-lookup"><span data-stu-id="4e6e9-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="4e6e9-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="4e6e9-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e6e9-108">Parameters</span></span>

<span data-ttu-id="4e6e9-109">Нет</span><span class="sxs-lookup"><span data-stu-id="4e6e9-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4e6e9-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="4e6e9-110">Examples</span></span>
<span data-ttu-id="4e6e9-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6e9-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="4e6e9-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="4e6e9-112">Example 1</span></span>

<span data-ttu-id="4e6e9-113">В следующем примере показано текущую папку, где хранятся файлы конфигурации и виртуальной машины из облака соединитель компонентов:</span><span class="sxs-lookup"><span data-stu-id="4e6e9-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="4e6e9-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4e6e9-114">Detailed Description</span></span>
<span data-ttu-id="4e6e9-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6e9-115"></span></span>

<span data-ttu-id="4e6e9-116">Показывает командлет Get-CcApplianceDirectory, где хранятся все файлы конфигурации и виртуальной машины, журналы и внешние сертификаты для устройства соединителя облачных.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="4e6e9-117">Устройство для каждого соединителя облачных состоит из четырех компонентов: сервер-посредник, центрального хранилища управления, пограничный сервер и контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="4e6e9-118">Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="4e6e9-119">Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4e6e9-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="4e6e9-120">Input Types</span></span>
<span data-ttu-id="4e6e9-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6e9-121"></span></span>

<span data-ttu-id="4e6e9-p104">Нет. Командлет Get-CCApplianceDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4e6e9-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="4e6e9-124">Return Types</span></span>
<span data-ttu-id="4e6e9-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6e9-125"></span></span>

<span data-ttu-id="4e6e9-126">Команда возвращает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="4e6e9-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e6e9-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4e6e9-127">See also</span></span>
<span data-ttu-id="4e6e9-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4e6e9-128"></span></span>

[<span data-ttu-id="4e6e9-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4e6e9-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

