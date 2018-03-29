---
title: Export-CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="2dcde-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="2dcde-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="2dcde-p102">Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.</span><span class="sxs-lookup"><span data-stu-id="2dcde-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="2dcde-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2dcde-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="2dcde-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dcde-108">Parameters</span></span>

<span data-ttu-id="2dcde-109">Нет</span><span class="sxs-lookup"><span data-stu-id="2dcde-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2dcde-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="2dcde-110">Examples</span></span>
<span data-ttu-id="2dcde-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2dcde-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="2dcde-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="2dcde-112">Example 1</span></span>

<span data-ttu-id="2dcde-113">В следующем примере файлы для загрузки пример файла конфигурации с сайта корпорации Майкрософт и записывает в каталоге appliance appliance облачных соединителя:</span><span class="sxs-lookup"><span data-stu-id="2dcde-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="2dcde-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="2dcde-114">Detailed Description</span></span>
<span data-ttu-id="2dcde-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2dcde-115"></span></span>

<span data-ttu-id="2dcde-116">Текущая версия облачных соединителя необходимо указать несколько параметров в INI-файла; Например, для таких параметров IP-адреса виртуальных машин для облачных компоненты, имена компонентов, параметры шлюза и т. д.</span><span class="sxs-lookup"><span data-stu-id="2dcde-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="2dcde-117">Этот командлет, при запуске на главном компьютере соединителя облачных файлы для загрузки примера INI-файле с примерами настройки с сайта корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2dcde-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="2dcde-118">Командлет записывает файл в каталоге appliance appliance облачных соединителя.</span><span class="sxs-lookup"><span data-stu-id="2dcde-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="2dcde-119">С помощью командлета Set-CcApplianceDirectory указан каталог устройства.</span><span class="sxs-lookup"><span data-stu-id="2dcde-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2dcde-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="2dcde-120">Input Types</span></span>
<span data-ttu-id="2dcde-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dcde-121"></span></span>

<span data-ttu-id="2dcde-p104">Нет. Командлет Export-CcConfigurationSampleFile не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="2dcde-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="2dcde-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="2dcde-124">Return Types</span></span>
<span data-ttu-id="2dcde-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dcde-125"></span></span>

<span data-ttu-id="2dcde-126">Нет</span><span class="sxs-lookup"><span data-stu-id="2dcde-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dcde-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2dcde-127">See also</span></span>
<span data-ttu-id="2dcde-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dcde-128"></span></span>

[<span data-ttu-id="2dcde-129">SET-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2dcde-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

