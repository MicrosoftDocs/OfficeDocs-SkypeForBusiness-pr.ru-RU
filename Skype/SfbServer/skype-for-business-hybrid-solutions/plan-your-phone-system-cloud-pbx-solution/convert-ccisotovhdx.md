---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Этот Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) с помощью предоставленного клиентом ISO-файла Windows Server 2012 R2. VHDX-файл будет использоваться во время развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802429"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="c34ad-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="c34ad-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="c34ad-105">Этот Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) с помощью предоставленного клиентом ISO-файла Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c34ad-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="c34ad-106">VHDX-файл будет использоваться во время развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c34ad-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="c34ad-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c34ad-107">Parameters</span></span>

|<span data-ttu-id="c34ad-108">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c34ad-108">**Parameter**</span></span>|<span data-ttu-id="c34ad-109">**Required**</span><span class="sxs-lookup"><span data-stu-id="c34ad-109">**Required**</span></span>|<span data-ttu-id="c34ad-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c34ad-110">**Type**</span></span>|<span data-ttu-id="c34ad-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c34ad-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c34ad-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="c34ad-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="c34ad-113">Обязательный</span><span class="sxs-lookup"><span data-stu-id="c34ad-113">Required</span></span> <br/> |<span data-ttu-id="c34ad-114">System.String</span><span class="sxs-lookup"><span data-stu-id="c34ad-114">System.String</span></span>  <br/> | <span data-ttu-id="c34ad-115">Путь к ISO-файлу Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="c34ad-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="c34ad-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="c34ad-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="c34ad-117">Необязательный</span><span class="sxs-lookup"><span data-stu-id="c34ad-117">Optional</span></span>  <br/> |<span data-ttu-id="c34ad-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c34ad-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c34ad-119">Если во время обновления Windows процесс преобразования не удается, можно попытаться настроить сеть или прокси-сервер и обновить Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="c34ad-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="c34ad-120">После выполнения ручной работы можно запустить этот cmdlet с параметром -GeneralizeOnly и выполнить оставшиеся задания.</span><span class="sxs-lookup"><span data-stu-id="c34ad-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="c34ad-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="c34ad-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="c34ad-122">Необязательный</span><span class="sxs-lookup"><span data-stu-id="c34ad-122">Optional</span></span>  <br/> |<span data-ttu-id="c34ad-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c34ad-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="c34ad-124">Для обновления Windows может потребоваться ручная настройка сети или прокси-сервера на базовой ВМ.</span><span class="sxs-lookup"><span data-stu-id="c34ad-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="c34ad-125">Если этот параметр задан, процесс преобразования будет приостановлен до обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="c34ad-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="c34ad-126">После настройки вручную можно возобновить процесс.</span><span class="sxs-lookup"><span data-stu-id="c34ad-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="c34ad-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="c34ad-127">Examples</span></span>
<span data-ttu-id="c34ad-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c34ad-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="c34ad-129">Пример 1</span><span class="sxs-lookup"><span data-stu-id="c34ad-129">Example 1</span></span>

<span data-ttu-id="c34ad-130">В следующем примере базовый VHDX-файл подготавливается с помощью ISO-файла Windows Server 2012 R2, расположенного по адресу C:\Windows_Server_2012_R2-EN-US-x64.ISO:</span><span class="sxs-lookup"><span data-stu-id="c34ad-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="c34ad-131">Пример 2</span><span class="sxs-lookup"><span data-stu-id="c34ad-131">Example 2</span></span>

<span data-ttu-id="c34ad-132">Сбой Convert-CcIsoToVhdx во время обновления Windows может быть некорректной конфигурацией сети или прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c34ad-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="c34ad-133">Вы можете следовать инструкциям в сообщении об ошибке и войти на базовую виртуальную машину, чтобы устранить проблему и обновить Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="c34ad-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="c34ad-134">После выполнения работы вручную запустите его еще раз с параметром -GeneralizeOnly, чтобы завершить оставшиеся задания:</span><span class="sxs-lookup"><span data-stu-id="c34ad-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="c34ad-135">Пример 3</span><span class="sxs-lookup"><span data-stu-id="c34ad-135">Example 3</span></span>

<span data-ttu-id="c34ad-136">Если для обновления Windows требуется ручная настройка, можно использовать параметр -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="c34ad-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="c34ad-137">С помощью этого параметра Cloud Connector будет приостановлен до обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="c34ad-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="c34ad-138">Затем можно выполнить настройку вручную и возобновить процесс преобразования следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c34ad-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="c34ad-139">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c34ad-139">Detailed Description</span></span>
<span data-ttu-id="c34ad-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c34ad-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="c34ad-141">Сначала Convert-CcIsoToVhdx создается базовая VM, устанавливаются некоторые основные компоненты, от которых зависит Cloud Connector, а затем устанавливаются обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="c34ad-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="c34ad-142">Наконец, он обучает виртуальную машину (sysprep) для получения базового VHDX-файла, который будет использоваться виртуальными машинами устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c34ad-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="c34ad-143">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="c34ad-143">Input Types</span></span>
<span data-ttu-id="c34ad-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c34ad-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="c34ad-145">Нет.</span><span class="sxs-lookup"><span data-stu-id="c34ad-145">None.</span></span> <span data-ttu-id="c34ad-146">Этот Convert-CcIsoToVhdx не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="c34ad-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="c34ad-147">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="c34ad-147">Return Types</span></span>
<span data-ttu-id="c34ad-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c34ad-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c34ad-149">Нет</span><span class="sxs-lookup"><span data-stu-id="c34ad-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c34ad-150">См. также</span><span class="sxs-lookup"><span data-stu-id="c34ad-150">See also</span></span>
<span data-ttu-id="c34ad-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c34ad-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="c34ad-152">Нет</span><span class="sxs-lookup"><span data-stu-id="c34ad-152">None</span></span>
  

