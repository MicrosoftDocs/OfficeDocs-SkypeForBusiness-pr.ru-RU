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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287384"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="9f203-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="9f203-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="9f203-p102">Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.</span><span class="sxs-lookup"><span data-stu-id="9f203-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="9f203-107">Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="9f203-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="9f203-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f203-108">Parameters</span></span>

<span data-ttu-id="9f203-109">Нет</span><span class="sxs-lookup"><span data-stu-id="9f203-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="9f203-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f203-110">Examples</span></span>
<span data-ttu-id="9f203-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9f203-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="9f203-112">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9f203-112">Example 1</span></span>

<span data-ttu-id="9f203-113">В следующем примере файл конфигурации примера загружается с сайта Майкрософт и записывается в каталог управляющего устройства облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="9f203-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="9f203-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9f203-114">Detailed Description</span></span>
<span data-ttu-id="9f203-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9f203-115"></span></span>

<span data-ttu-id="9f203-116">Для текущей версии облачного соединителя требуется предоставить несколько параметров в ini-файле. Например, такие параметры, как IP-адреса виртуальных машин для компонентов облачного соединителя, имена компонентов, параметры шлюза и т. д.</span><span class="sxs-lookup"><span data-stu-id="9f203-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="9f203-117">Этот командлет при запуске на главном компьютере облачного соединителя, загружает образец ini-файла с примерами конфигурации на сайте Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9f203-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="9f203-118">Командлет записывает файл в каталог управляющего устройства облачного соединителя.</span><span class="sxs-lookup"><span data-stu-id="9f203-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="9f203-119">Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.</span><span class="sxs-lookup"><span data-stu-id="9f203-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="9f203-120">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9f203-120">Input Types</span></span>
<span data-ttu-id="9f203-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f203-121"></span></span>

<span data-ttu-id="9f203-p104">Нет. Командлет Export-CcConfigurationSampleFile не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9f203-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="9f203-124">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9f203-124">Return Types</span></span>
<span data-ttu-id="9f203-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f203-125"></span></span>

<span data-ttu-id="9f203-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9f203-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f203-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9f203-127">See also</span></span>
<span data-ttu-id="9f203-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9f203-128"></span></span>

[<span data-ttu-id="9f203-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="9f203-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

