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
description: Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799859"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="f8c86-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8c86-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="f8c86-104">Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="f8c86-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="f8c86-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="f8c86-105">Examples</span></span>
<span data-ttu-id="f8c86-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f8c86-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="f8c86-107">Example 1</span></span>

<span data-ttu-id="f8c86-108">В следующем примере копируется Клаудконнектор. ini из каталога устройства в экземпляре облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор:</span><span class="sxs-lookup"><span data-stu-id="f8c86-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="f8c86-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f8c86-109">Detailed Description</span></span>
<span data-ttu-id="f8c86-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="f8c86-111">Этот командлет копирует Клаудконнектор. ini из каталога управляющего устройства облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="f8c86-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="f8c86-112">Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.</span><span class="sxs-lookup"><span data-stu-id="f8c86-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="f8c86-113">Командлет перезапишет существующий файл в%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="f8c86-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="f8c86-114">Эта команда применима к Cloud Connector Edition версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f8c86-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f8c86-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8c86-115">Parameters</span></span>
<span data-ttu-id="f8c86-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="f8c86-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="f8c86-117">**Parameter**</span></span>|<span data-ttu-id="f8c86-118">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="f8c86-118">**Required**</span></span>|<span data-ttu-id="f8c86-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f8c86-119">**Type**</span></span>|<span data-ttu-id="f8c86-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f8c86-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8c86-121">Force</span><span class="sxs-lookup"><span data-stu-id="f8c86-121">Force</span></span>  <br/> |<span data-ttu-id="f8c86-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="f8c86-122">Optional</span></span>  <br/> |<span data-ttu-id="f8c86-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f8c86-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f8c86-124">Перезаписать существующий файл в%Системдриве%\програмдата\клаудконнектор без уведомления.</span><span class="sxs-lookup"><span data-stu-id="f8c86-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f8c86-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="f8c86-125">Input Types</span></span>
<span data-ttu-id="f8c86-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="f8c86-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="f8c86-127">None.</span></span> <span data-ttu-id="f8c86-128">Командлет Import-Ккконфигуратион не поддерживает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="f8c86-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f8c86-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="f8c86-129">Return Types</span></span>
<span data-ttu-id="f8c86-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="f8c86-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="f8c86-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8c86-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f8c86-132">See also</span></span>
<span data-ttu-id="f8c86-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c86-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="f8c86-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8c86-134">Export-CcConfiguration</span></span>
  

