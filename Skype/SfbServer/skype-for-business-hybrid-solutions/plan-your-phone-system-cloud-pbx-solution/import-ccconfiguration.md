---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на хост-сервер Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799859"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="b8754-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b8754-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="b8754-104">Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на хост-сервер Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b8754-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b8754-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8754-105">Examples</span></span>
<span data-ttu-id="b8754-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b8754-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="b8754-107">Example 1</span></span>

<span data-ttu-id="b8754-108">В следующем примере CloudConnector.ini из каталога устройства экземпляра Cloud Connector в каталог %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="b8754-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="b8754-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b8754-109">Detailed Description</span></span>
<span data-ttu-id="b8754-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="b8754-111">Этот cmdlet копирует CloudConnector.ini из каталога устройства устройства Cloud Connector в каталог %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="b8754-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="b8754-112">Каталог устройства указывается с помощью Set-CcApplianceDirectory устройства.</span><span class="sxs-lookup"><span data-stu-id="b8754-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="b8754-113">Он перезапишет существующий файл в папке %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="b8754-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="b8754-114">Эта команда применяется к Cloud Connector Edition версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="b8754-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b8754-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8754-115">Parameters</span></span>
<span data-ttu-id="b8754-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="b8754-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="b8754-117">**Parameter**</span></span>|<span data-ttu-id="b8754-118">**Required**</span><span class="sxs-lookup"><span data-stu-id="b8754-118">**Required**</span></span>|<span data-ttu-id="b8754-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="b8754-119">**Type**</span></span>|<span data-ttu-id="b8754-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b8754-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8754-121">Force</span><span class="sxs-lookup"><span data-stu-id="b8754-121">Force</span></span>  <br/> |<span data-ttu-id="b8754-122">Необязательный</span><span class="sxs-lookup"><span data-stu-id="b8754-122">Optional</span></span>  <br/> |<span data-ttu-id="b8754-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b8754-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b8754-124">Перезаписать существующий файл в папке %SystemDrive%\ProgramData\CloudConnector без уведомления.</span><span class="sxs-lookup"><span data-stu-id="b8754-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b8754-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="b8754-125">Input Types</span></span>
<span data-ttu-id="b8754-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="b8754-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="b8754-127">None.</span></span> <span data-ttu-id="b8754-128">Этот Import-CcConfiguration не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="b8754-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b8754-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b8754-129">Return Types</span></span>
<span data-ttu-id="b8754-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="b8754-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="b8754-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8754-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b8754-132">See also</span></span>
<span data-ttu-id="b8754-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b8754-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="b8754-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="b8754-134">Export-CcConfiguration</span></span>
  

