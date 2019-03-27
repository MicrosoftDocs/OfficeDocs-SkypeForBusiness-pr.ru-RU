---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.
ms.openlocfilehash: 497568f45fad6b4363581785bf0be95eabfeaebf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896625"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="92cf6-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="92cf6-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="92cf6-104">Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="92cf6-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="92cf6-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="92cf6-105">Examples</span></span>
<span data-ttu-id="92cf6-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="92cf6-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="92cf6-107">Example 1</span></span>

<span data-ttu-id="92cf6-108">В следующем примере копируется CloudConnector.ini из каталога appliance экземпляра соединителя Cloud %SystemDrive%\ProgramData\CloudConnector каталог:</span><span class="sxs-lookup"><span data-stu-id="92cf6-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="92cf6-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="92cf6-109">Detailed Description</span></span>
<span data-ttu-id="92cf6-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-110"></span></span>

<span data-ttu-id="92cf6-111">Этот командлет копирует CloudConnector.ini из каталога appliance устройства соединителя облака в каталог %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="92cf6-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="92cf6-112">С помощью командлета Set-CcApplianceDirectory указан каталог устройства.</span><span class="sxs-lookup"><span data-stu-id="92cf6-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="92cf6-113">Командлет будет перезаписать существующий файл в папке % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="92cf6-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="92cf6-114">Эта команда применяется к Edition соединителя облачных версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="92cf6-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="92cf6-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="92cf6-115">Parameters</span></span>
<span data-ttu-id="92cf6-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-116"></span></span>

|<span data-ttu-id="92cf6-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="92cf6-117">**Parameter**</span></span>|<span data-ttu-id="92cf6-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="92cf6-118">**Required**</span></span>|<span data-ttu-id="92cf6-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="92cf6-119">**Type**</span></span>|<span data-ttu-id="92cf6-120">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="92cf6-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92cf6-121">Force</span><span class="sxs-lookup"><span data-stu-id="92cf6-121">Force</span></span>  <br/> |<span data-ttu-id="92cf6-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="92cf6-122">Optional</span></span>  <br/> |<span data-ttu-id="92cf6-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="92cf6-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="92cf6-124">Перезапись существующего файла в %SystemDrive%\ProgramData\CloudConnector без уведомления.</span><span class="sxs-lookup"><span data-stu-id="92cf6-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="92cf6-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="92cf6-125">Input Types</span></span>
<span data-ttu-id="92cf6-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-126"></span></span>

<span data-ttu-id="92cf6-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="92cf6-127">None.</span></span> <span data-ttu-id="92cf6-128">Командлет Import-CcConfiguration не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="92cf6-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="92cf6-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="92cf6-129">Return Types</span></span>
<span data-ttu-id="92cf6-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-130"></span></span>

<span data-ttu-id="92cf6-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="92cf6-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92cf6-132">См. также</span><span class="sxs-lookup"><span data-stu-id="92cf6-132">See also</span></span>
<span data-ttu-id="92cf6-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="92cf6-133"></span></span>

<span data-ttu-id="92cf6-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="92cf6-134">Export-CcConfiguration</span></span>
  

