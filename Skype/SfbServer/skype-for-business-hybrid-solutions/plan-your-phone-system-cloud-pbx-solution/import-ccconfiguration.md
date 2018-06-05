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
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569728"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="bfed4-103">Импорт CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfed4-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="bfed4-104">Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="bfed4-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="bfed4-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="bfed4-105">Examples</span></span>
<span data-ttu-id="bfed4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="bfed4-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="bfed4-107">Example 1</span></span>

<span data-ttu-id="bfed4-108">В следующем примере копируется CloudConnector.ini из каталога appliance экземпляра соединителя Cloud %SystemDrive%\ProgramData\CloudConnector каталог:</span><span class="sxs-lookup"><span data-stu-id="bfed4-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="bfed4-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="bfed4-109">Detailed Description</span></span>
<span data-ttu-id="bfed4-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-110"></span></span>

<span data-ttu-id="bfed4-111">Этот командлет копирует CloudConnector.ini из каталога appliance устройства соединителя облака в каталог %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="bfed4-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="bfed4-112">С помощью командлета Set-CcApplianceDirectory указан каталог устройства.</span><span class="sxs-lookup"><span data-stu-id="bfed4-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="bfed4-113">Командлет будет перезаписать существующий файл в папке % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="bfed4-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="bfed4-114">Эта команда применяется к Edition соединителя облачных версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="bfed4-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bfed4-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfed4-115">Parameters</span></span>
<span data-ttu-id="bfed4-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-116"></span></span>

|<span data-ttu-id="bfed4-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="bfed4-117">**Parameter**</span></span>|<span data-ttu-id="bfed4-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="bfed4-118">**Required**</span></span>|<span data-ttu-id="bfed4-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="bfed4-119">**Type**</span></span>|<span data-ttu-id="bfed4-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bfed4-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bfed4-121">Force</span><span class="sxs-lookup"><span data-stu-id="bfed4-121">Force</span></span>  <br/> |<span data-ttu-id="bfed4-122"> Необязательно</span><span class="sxs-lookup"><span data-stu-id="bfed4-122">Optional</span></span>  <br/> |<span data-ttu-id="bfed4-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="bfed4-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="bfed4-124">Перезапись существующего файла в %SystemDrive%\ProgramData\CloudConnector без уведомления.</span><span class="sxs-lookup"><span data-stu-id="bfed4-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bfed4-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="bfed4-125">Input Types</span></span>
<span data-ttu-id="bfed4-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-126"></span></span>

<span data-ttu-id="bfed4-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="bfed4-127">None.</span></span> <span data-ttu-id="bfed4-128">Командлет Import-CcConfiguration не принимает входные данные.</span><span class="sxs-lookup"><span data-stu-id="bfed4-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bfed4-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="bfed4-129">Return Types</span></span>
<span data-ttu-id="bfed4-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-130"></span></span>

<span data-ttu-id="bfed4-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="bfed4-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bfed4-132">См. также</span><span class="sxs-lookup"><span data-stu-id="bfed4-132">See also</span></span>
<span data-ttu-id="bfed4-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bfed4-133"></span></span>

<span data-ttu-id="bfed4-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfed4-134">Export-CcConfiguration</span></span>
  

