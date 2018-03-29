---
title: Convert-CcIsoToVhdx
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Командлет Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="afb03-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="afb03-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="afb03-p102">Командлет Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="afb03-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="afb03-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="afb03-107">Parameters</span></span>

|<span data-ttu-id="afb03-108">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="afb03-108">**Parameter**</span></span>|<span data-ttu-id="afb03-109">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="afb03-109">**Required**</span></span>|<span data-ttu-id="afb03-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="afb03-110">**Type**</span></span>|<span data-ttu-id="afb03-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="afb03-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="afb03-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="afb03-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="afb03-113">Обязательно</span><span class="sxs-lookup"><span data-stu-id="afb03-113">Required</span></span> <br/> |<span data-ttu-id="afb03-114">System.String</span><span class="sxs-lookup"><span data-stu-id="afb03-114">System.String</span></span>  <br/> | <span data-ttu-id="afb03-115">Путь к ISO-файлу образа с Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="afb03-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="afb03-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="afb03-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="afb03-117">Необязательно</span><span class="sxs-lookup"><span data-stu-id="afb03-117">Optional</span></span>  <br/> |<span data-ttu-id="afb03-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="afb03-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="afb03-p103">Если во время обновления Windows произойдет сбой процесса преобразования, вы можете попробовать настроить сеть или прокси-сервер и выполнить обновление Windows вручную. После выполнения задачи вручную вы можете запустить этот командлет с параметром -GeneralizeOnly, чтобы выполнить оставшиеся шаги. </span><span class="sxs-lookup"><span data-stu-id="afb03-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="afb03-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="afb03-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="afb03-122">Необязательно</span><span class="sxs-lookup"><span data-stu-id="afb03-122">Optional</span></span>  <br/> |<span data-ttu-id="afb03-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="afb03-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="afb03-p104">Для обновления Windows необходимо вручную задать некоторые параметры сети или прокси-сервера на базовой виртуальной машине. Если указан этот параметр, процесс преобразования будет приостановлен до обновления Windows. После того, как нужные параметры будут заданы вручную, этот процесс можно возобновить. </span><span class="sxs-lookup"><span data-stu-id="afb03-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="afb03-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="afb03-127">Examples</span></span>
<span data-ttu-id="afb03-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="afb03-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="afb03-129">Пример 1</span><span class="sxs-lookup"><span data-stu-id="afb03-129">Example 1</span></span>

<span data-ttu-id="afb03-130">В следующем примере подготавливается базовый VHDX-файл с использованием ISO-файла с образом Windows Server 2012 R2, который расположен в каталоге "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span><span class="sxs-lookup"><span data-stu-id="afb03-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="afb03-131">Пример 2</span><span class="sxs-lookup"><span data-stu-id="afb03-131">Example 2</span></span>

<span data-ttu-id="afb03-132">В случае сбоя командлету Convert-CcIsoToVhdx во время обновления Windows, возможно, из-за неправильной сети и прокси-сервером.</span><span class="sxs-lookup"><span data-stu-id="afb03-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="afb03-133">Вы можете выполнить инструкции, представленные в сообщении об ошибке, и войти в систему базовой виртуальной машины, чтобы устранить проблему и обновить Windows вручную.</span><span class="sxs-lookup"><span data-stu-id="afb03-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="afb03-134">После выполнения задачи вручную вы можете запустить этот командлет еще раз с параметром -GeneralizeOnly, чтобы выполнить оставшиеся шаги:</span><span class="sxs-lookup"><span data-stu-id="afb03-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="afb03-135">Пример 3</span><span class="sxs-lookup"><span data-stu-id="afb03-135">Example 3</span></span>

<span data-ttu-id="afb03-136">Если для обновления Windows требуется выполнить настройку параметров вручную, используйте параметр -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="afb03-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="afb03-137">С помощью этого параметра соединителя облачных возникнет пауза перед процесса обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="afb03-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="afb03-138">После этого вы можете выполнить настройку вручную и затем возобновить процесс преобразования:</span><span class="sxs-lookup"><span data-stu-id="afb03-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="afb03-139">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="afb03-139">Detailed Description</span></span>
<span data-ttu-id="afb03-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="afb03-140"></span></span>

<span data-ttu-id="afb03-141">Командлет Convert-CcIsoToVhdx создает основу виртуальной Машины во-первых, устанавливает некоторые основные компоненты, что соединитель облачных зависит от того, а затем устанавливает обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="afb03-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="afb03-142">И, наконец обобщает виртуальной машины (sysprep) для получения базового файла VHDX, который будет использоваться с виртуальных машин appliance облачных соединителя.</span><span class="sxs-lookup"><span data-stu-id="afb03-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="afb03-143">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="afb03-143">Input Types</span></span>
<span data-ttu-id="afb03-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="afb03-144"></span></span>

<span data-ttu-id="afb03-p108">Нет. Командлет Convert-CcIsoToVhdx не принимает входные данные по конвейеру. </span><span class="sxs-lookup"><span data-stu-id="afb03-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="afb03-147">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="afb03-147">Return Types</span></span>
<span data-ttu-id="afb03-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="afb03-148"></span></span>

<span data-ttu-id="afb03-149">Нет</span><span class="sxs-lookup"><span data-stu-id="afb03-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="afb03-150">См. также</span><span class="sxs-lookup"><span data-stu-id="afb03-150">See also</span></span>
<span data-ttu-id="afb03-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="afb03-151"></span></span>

<span data-ttu-id="afb03-152">Нет</span><span class="sxs-lookup"><span data-stu-id="afb03-152">None</span></span>
  

