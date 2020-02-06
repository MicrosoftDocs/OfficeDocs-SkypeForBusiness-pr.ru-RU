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
description: Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801009"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="b1aef-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="b1aef-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="b1aef-p102">Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.</span><span class="sxs-lookup"><span data-stu-id="b1aef-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="b1aef-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="b1aef-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="b1aef-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1aef-108">Parameters</span></span>

<span data-ttu-id="b1aef-109">Нет</span><span class="sxs-lookup"><span data-stu-id="b1aef-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b1aef-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="b1aef-110">Examples</span></span>
<span data-ttu-id="b1aef-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b1aef-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="b1aef-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="b1aef-112">Example 1</span></span>

<span data-ttu-id="b1aef-113">В следующем примере файл конфигурации примера загружается с сайта Майкрософт и записывается в каталог управляющего устройства облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="b1aef-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="b1aef-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b1aef-114">Detailed Description</span></span>
<span data-ttu-id="b1aef-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b1aef-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="b1aef-116">Для текущей версии облачного соединителя требуется предоставить несколько параметров в ini-файле. Например, такие параметры, как IP-адреса виртуальных машин для компонентов облачного соединителя, имена компонентов, параметры шлюза и т. д.</span><span class="sxs-lookup"><span data-stu-id="b1aef-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="b1aef-117">Этот командлет при запуске на главном компьютере облачного соединителя, загружает образец ini-файла с примерами конфигурации на сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b1aef-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="b1aef-118">Командлет записывает файл в каталог управляющего устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="b1aef-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="b1aef-119">Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.</span><span class="sxs-lookup"><span data-stu-id="b1aef-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b1aef-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="b1aef-120">Input Types</span></span>
<span data-ttu-id="b1aef-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1aef-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="b1aef-p104">Нет. Командлет Export-CcConfigurationSampleFile не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b1aef-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="b1aef-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="b1aef-124">Return Types</span></span>
<span data-ttu-id="b1aef-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1aef-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="b1aef-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="b1aef-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1aef-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b1aef-127">See also</span></span>
<span data-ttu-id="b1aef-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b1aef-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="b1aef-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b1aef-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

