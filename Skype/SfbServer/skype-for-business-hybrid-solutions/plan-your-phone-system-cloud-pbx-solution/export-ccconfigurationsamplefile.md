---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. Вы можете изменить и переименовать файл для развертывания.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801009"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="8fa68-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="8fa68-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="8fa68-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span><span class="sxs-lookup"><span data-stu-id="8fa68-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="8fa68-106">Вы можете изменить и переименовать файл для развертывания.</span><span class="sxs-lookup"><span data-stu-id="8fa68-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="8fa68-107">Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="8fa68-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="8fa68-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fa68-108">Parameters</span></span>

<span data-ttu-id="8fa68-109">Нет</span><span class="sxs-lookup"><span data-stu-id="8fa68-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8fa68-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="8fa68-110">Examples</span></span>
<span data-ttu-id="8fa68-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8fa68-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8fa68-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="8fa68-112">Example 1</span></span>

<span data-ttu-id="8fa68-113">В следующем примере скачивает пример файла конфигурации с сайта Майкрософт и записывает его в каталог устройства устройства Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="8fa68-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="8fa68-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="8fa68-114">Detailed Description</span></span>
<span data-ttu-id="8fa68-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8fa68-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8fa68-116">В текущей версии Cloud Connector необходимо укажет несколько параметров в INI-файле; например, такие параметры, как IP-адреса виртуальных машин для компонентов Cloud Connector, имена компонентов, параметры шлюза и так далее.</span><span class="sxs-lookup"><span data-stu-id="8fa68-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="8fa68-117">Этот cmdlet при запуске на хост-компьютере Cloud Connector скачивает пример INI-файла с примерами конфигурации с сайта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8fa68-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="8fa68-118">Этот файл записывается в каталог устройств устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="8fa68-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="8fa68-119">Каталог устройства указывается с помощью Set-CcApplianceDirectory устройства.</span><span class="sxs-lookup"><span data-stu-id="8fa68-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8fa68-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="8fa68-120">Input Types</span></span>
<span data-ttu-id="8fa68-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8fa68-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8fa68-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="8fa68-122">None.</span></span> <span data-ttu-id="8fa68-123">Этот Export-CcConfigurationSampleFile не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="8fa68-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="8fa68-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="8fa68-124">Return Types</span></span>
<span data-ttu-id="8fa68-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8fa68-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8fa68-126">Нет</span><span class="sxs-lookup"><span data-stu-id="8fa68-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8fa68-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8fa68-127">See also</span></span>
<span data-ttu-id="8fa68-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8fa68-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8fa68-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="8fa68-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

