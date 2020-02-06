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
description: Командлет Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802429"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Командлет Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) на основе предоставленного клиентом ISO-файла с образом Windows Server 2012 R2. VHDX-файл используется в процессе развертывания Skype для бизнеса Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Параметры

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Обязательно <br/> |System.String  <br/> | Путь к ISO-файлу образа с Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Если во время обновления Windows произойдет сбой процесса преобразования, вы можете попробовать настроить сеть или прокси-сервер и выполнить обновление Windows вручную. После выполнения задачи вручную вы можете запустить этот командлет с параметром -GeneralizeOnly, чтобы выполнить оставшиеся шаги.   <br/> |
|PauseBeforeUpdate  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Для обновления Windows необходимо вручную задать некоторые параметры сети или прокси-сервера на базовой виртуальной машине. Если указан этот параметр, процесс преобразования будет приостановлен до обновления Windows. После того, как нужные параметры будут заданы вручную, этот процесс можно возобновить.   <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере подготавливается базовый VHDX-файл с использованием ISO-файла с образом Windows Server 2012 R2, который расположен в каталоге "C:\Windows_Server_2012_R2-EN-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Пример 2

Если командлет Convert-КЦисотовхдкс завершается сбоем во время обновления Windows, возможно, это вызвано неверной конфигурацией сети или прокси-сервера. Вы можете выполнить инструкции, представленные в сообщении об ошибке, и войти в систему базовой виртуальной машины, чтобы устранить проблему и обновить Windows вручную. После выполнения задачи вручную вы можете запустить этот командлет еще раз с параметром -GeneralizeOnly, чтобы выполнить оставшиеся шаги: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Пример 3

Если для обновления Windows требуется выполнить настройку параметров вручную, используйте параметр -PauseBeforeUpdate. С помощью этого параметра облачный соединитель будет приостановлен до процесса обновления Windows. После этого вы можете выполнить настройку вручную и затем возобновить процесс преобразования:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Convert-КЦисотовхдкс сначала создает базовую виртуальную машину, устанавливает некоторые основные компоненты, от которых зависит облачный соединитель, а затем устанавливает обновления Windows. Наконец, она обобщает виртуальную машину (Sysprep) для получения базового VHDX-файла, который будет использоваться виртуальными машинами устройства облачного соединителя. 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Convert-CcIsoToVhdx не принимает входные данные по конвейеру.  
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

