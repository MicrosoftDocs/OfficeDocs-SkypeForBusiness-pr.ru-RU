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
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Этот Convert-CcIsoToVhdx создает файл базового виртуального жесткого диска (VHDX) с помощью предоставленного клиентом ISO-файла Windows Server 2012 R2. VHDX-файл будет использоваться во время развертывания Skype для бизнеса Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Параметры

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Обязательный <br/> |System.String  <br/> | Путь к ISO-файлу Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Если во время обновления Windows процесс преобразования не удается, можно попытаться настроить сеть или прокси-сервер и обновить Windows вручную. После выполнения ручной работы можно запустить этот cmdlet с параметром -GeneralizeOnly и выполнить оставшиеся задания.  <br/> |
|PauseBeforeUpdate  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Для обновления Windows может потребоваться ручная настройка сети или прокси-сервера на базовой ВМ. Если этот параметр задан, процесс преобразования будет приостановлен до обновления Windows. После настройки вручную можно возобновить процесс.  <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере базовый VHDX-файл подготавливается с помощью ISO-файла Windows Server 2012 R2, расположенного по адресу C:\Windows_Server_2012_R2-EN-US-x64.ISO: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Пример 2

Сбой Convert-CcIsoToVhdx во время обновления Windows может быть некорректной конфигурацией сети или прокси-сервера. Вы можете следовать инструкциям в сообщении об ошибке и войти на базовую виртуальную машину, чтобы устранить проблему и обновить Windows вручную. После выполнения работы вручную запустите его еще раз с параметром -GeneralizeOnly, чтобы завершить оставшиеся задания: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Пример 3

Если для обновления Windows требуется ручная настройка, можно использовать параметр -PauseBeforeUpdate. С помощью этого параметра Cloud Connector будет приостановлен до обновления Windows. Затем можно выполнить настройку вручную и возобновить процесс преобразования следующим образом:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сначала Convert-CcIsoToVhdx создается базовая VM, устанавливаются некоторые основные компоненты, от которых зависит Cloud Connector, а затем устанавливаются обновления Windows. Наконец, он обучает виртуальную машину (sysprep) для получения базового VHDX-файла, который будет использоваться виртуальными машинами устройства Cloud Connector. 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Convert-CcIsoToVhdx не принимает конвейерные входные данные. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

