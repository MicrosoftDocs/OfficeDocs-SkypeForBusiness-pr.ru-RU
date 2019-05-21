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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287281"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="979e7-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="979e7-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="979e7-104">Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="979e7-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="979e7-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="979e7-105">Examples</span></span>
<span data-ttu-id="979e7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="979e7-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="979e7-107">Example 1</span></span>

<span data-ttu-id="979e7-108">В следующем примере копируется Клаудконнектор. ini из каталога устройства в экземпляре облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор:</span><span class="sxs-lookup"><span data-stu-id="979e7-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="979e7-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="979e7-109">Detailed Description</span></span>
<span data-ttu-id="979e7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-110"></span></span>

<span data-ttu-id="979e7-111">Этот командлет копирует Клаудконнектор. ini из каталога управляющего устройства облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="979e7-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="979e7-112">Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.</span><span class="sxs-lookup"><span data-stu-id="979e7-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="979e7-113">Командлет перезапишет существующий файл в%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="979e7-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="979e7-114">Эта команда применима к Cloud Connector Edition версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="979e7-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="979e7-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="979e7-115">Parameters</span></span>
<span data-ttu-id="979e7-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-116"></span></span>

|<span data-ttu-id="979e7-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="979e7-117">**Parameter**</span></span>|<span data-ttu-id="979e7-118">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="979e7-118">**Required**</span></span>|<span data-ttu-id="979e7-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="979e7-119">**Type**</span></span>|<span data-ttu-id="979e7-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="979e7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="979e7-121">Force</span><span class="sxs-lookup"><span data-stu-id="979e7-121">Force</span></span>  <br/> |<span data-ttu-id="979e7-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="979e7-122">Optional</span></span>  <br/> |<span data-ttu-id="979e7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="979e7-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="979e7-124">Перезаписать существующий файл в%Системдриве%\програмдата\клаудконнектор без уведомления.</span><span class="sxs-lookup"><span data-stu-id="979e7-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="979e7-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="979e7-125">Input Types</span></span>
<span data-ttu-id="979e7-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-126"></span></span>

<span data-ttu-id="979e7-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="979e7-127">None.</span></span> <span data-ttu-id="979e7-128">Командлет Import-Ккконфигуратион не поддерживает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="979e7-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="979e7-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="979e7-129">Return Types</span></span>
<span data-ttu-id="979e7-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-130"></span></span>

<span data-ttu-id="979e7-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="979e7-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="979e7-132">См. также</span><span class="sxs-lookup"><span data-stu-id="979e7-132">See also</span></span>
<span data-ttu-id="979e7-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="979e7-133"></span></span>

<span data-ttu-id="979e7-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="979e7-134">Export-CcConfiguration</span></span>
  

