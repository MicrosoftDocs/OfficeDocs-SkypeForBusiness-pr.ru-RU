---
title: Импорт CcConfiguration
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
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="c2c2d-103">Импорт CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c2c2d-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="c2c2d-104">Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="c2c2d-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="c2c2d-105">Examples</span></span>
<span data-ttu-id="c2c2d-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="c2c2d-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c2c2d-107">Example 1</span></span>

<span data-ttu-id="c2c2d-108">В следующем примере копируется CloudConnector.ini из каталога appliance экземпляра соединителя Cloud %SystemDrive%\ProgramData\CloudConnector каталог:</span><span class="sxs-lookup"><span data-stu-id="c2c2d-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="c2c2d-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c2c2d-109">Detailed Description</span></span>
<span data-ttu-id="c2c2d-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-110"></span></span>

<span data-ttu-id="c2c2d-111">Этот командлет копирует CloudConnector.ini из каталога appliance устройства соединителя облака в каталог %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="c2c2d-112">С помощью командлета Set-CcApplianceDirectory указан каталог устройства.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="c2c2d-113">Командлет будет перезаписать существующий файл в папке % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="c2c2d-114">Эта команда применяется к Edition соединителя облачных версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c2c2d-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2c2d-115">Parameters</span></span>
<span data-ttu-id="c2c2d-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-116"></span></span>

|<span data-ttu-id="c2c2d-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c2c2d-117">**Parameter**</span></span>|<span data-ttu-id="c2c2d-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="c2c2d-118">**Required**</span></span>|<span data-ttu-id="c2c2d-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c2c2d-119">**Type**</span></span>|<span data-ttu-id="c2c2d-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c2c2d-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2c2d-121">Force</span><span class="sxs-lookup"><span data-stu-id="c2c2d-121">Force</span></span>  <br/> |<span data-ttu-id="c2c2d-122"> Необязательно</span><span class="sxs-lookup"><span data-stu-id="c2c2d-122">Optional</span></span>  <br/> |<span data-ttu-id="c2c2d-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c2c2d-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c2c2d-124">Перезапись существующего файла в %SystemDrive%\ProgramData\CloudConnector без уведомления.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c2c2d-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c2c2d-125">Input Types</span></span>
<span data-ttu-id="c2c2d-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-126"></span></span>

<span data-ttu-id="c2c2d-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-127">None.</span></span> <span data-ttu-id="c2c2d-128">Командлет Import-CcConfiguration не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c2c2d-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c2c2d-129">Return Types</span></span>
<span data-ttu-id="c2c2d-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-130"></span></span>

<span data-ttu-id="c2c2d-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="c2c2d-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c2c2d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c2c2d-132">See also</span></span>
<span data-ttu-id="c2c2d-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c2d-133"></span></span>

<span data-ttu-id="c2c2d-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="c2c2d-134">Export-CcConfiguration</span></span>
  

