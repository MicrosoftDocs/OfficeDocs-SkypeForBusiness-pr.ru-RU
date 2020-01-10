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
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003339"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="9b792-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b792-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="9b792-104">Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="9b792-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="9b792-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="9b792-105">Examples</span></span>
<span data-ttu-id="9b792-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="9b792-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9b792-107">Example 1</span></span>

<span data-ttu-id="9b792-108">В следующем примере копируется Клаудконнектор. ini из каталога устройства в экземпляре облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор:</span><span class="sxs-lookup"><span data-stu-id="9b792-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="9b792-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9b792-109">Detailed Description</span></span>
<span data-ttu-id="9b792-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-110"></span></span>

<span data-ttu-id="9b792-111">Этот командлет копирует Клаудконнектор. ini из каталога управляющего устройства облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="9b792-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="9b792-112">Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.</span><span class="sxs-lookup"><span data-stu-id="9b792-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="9b792-113">Командлет перезапишет существующий файл в%Системдриве%\програмдата\клаудконнектор.</span><span class="sxs-lookup"><span data-stu-id="9b792-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="9b792-114">Эта команда применима к Cloud Connector Edition версии 2.0.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="9b792-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9b792-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b792-115">Parameters</span></span>
<span data-ttu-id="9b792-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-116"></span></span>

|<span data-ttu-id="9b792-117">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="9b792-117">**Parameter**</span></span>|<span data-ttu-id="9b792-118">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="9b792-118">**Required**</span></span>|<span data-ttu-id="9b792-119">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9b792-119">**Type**</span></span>|<span data-ttu-id="9b792-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9b792-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b792-121">Force</span><span class="sxs-lookup"><span data-stu-id="9b792-121">Force</span></span>  <br/> |<span data-ttu-id="9b792-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="9b792-122">Optional</span></span>  <br/> |<span data-ttu-id="9b792-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9b792-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="9b792-124">Перезаписать существующий файл в%Системдриве%\програмдата\клаудконнектор без уведомления.</span><span class="sxs-lookup"><span data-stu-id="9b792-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9b792-125">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9b792-125">Input Types</span></span>
<span data-ttu-id="9b792-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-126"></span></span>

<span data-ttu-id="9b792-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="9b792-127">None.</span></span> <span data-ttu-id="9b792-128">Командлет Import-Ккконфигуратион не поддерживает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="9b792-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9b792-129">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9b792-129">Return Types</span></span>
<span data-ttu-id="9b792-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-130"></span></span>

<span data-ttu-id="9b792-131">Нет.</span><span class="sxs-lookup"><span data-stu-id="9b792-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b792-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9b792-132">See also</span></span>
<span data-ttu-id="9b792-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9b792-133"></span></span>

<span data-ttu-id="9b792-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b792-134">Export-CcConfiguration</span></span>
  

