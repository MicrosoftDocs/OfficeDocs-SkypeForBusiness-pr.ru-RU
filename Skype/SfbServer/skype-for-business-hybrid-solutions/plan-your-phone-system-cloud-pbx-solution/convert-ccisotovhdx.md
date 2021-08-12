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
description: Этот Convert-CcIsoToVhdx создает базовый виртуальный жесткий дисковый файл (VHDX) с помощью клиентского Windows Server 2012 R2 ISO. Файл VHDX будет использоваться во время развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: d168155c918ba1e8a3a576e543eed6693d0fb6faa5bd4fc23efd8c95b2b50fa1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349551"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Этот Convert-CcIsoToVhdx создает базовый виртуальный жесткий дисковый файл (VHDX) с помощью клиентского Windows Server 2012 R2 ISO. Файл VHDX будет использоваться во время развертывания Skype для бизнеса Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Параметры

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Обязательный <br/> |System.String  <br/> | Путь к файлу ISO Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Если процесс преобразования не удается во время Windows обновления, можно попытаться настроить сеть/прокси и обновить Windows вручную. После выполнения ручной работы можно запустить этот комлет с параметром -GeneralizeOnly и выполнить оставшиеся задания.  <br/> |
|PauseBeforeUpdate  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Чтобы обновить Windows, может потребоваться ручная конфигурация сети и прокси в базовом VM. Процесс преобразования будет приостановлен до Windows обновления, если этот параметр предоставлен. После того как ручная конфигурация будет сделана, вы можете возобновить процесс.  <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере базовый VHDX-файл подготавливается с помощью файла ISO Windows Server 2012 R2, расположенного в "C:\Windows_Server_2012_R2-RU-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Пример 2

Если во время Convert-CcIsoToVhdx не удается Windows, это, вероятно, из-за неправильной конфигурации сети и прокси. Вы можете следовать инструкциям в сообщении об ошибке и войти в базовый виртуальный компьютер, чтобы устранить проблему и обновить Windows вручную. После выполнения ручной работы выполните этот список еще раз с параметром -GeneralizeOnly для выполнения оставшихся заданий: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Пример 3

Если для обновления Windows требуется ручная конфигурация, можно использовать параметр PauseBeforeUpdate. С помощью этого параметра облачный соединитатель приостанавливется перед Windows обновления. Затем можно выполнить ручную конфигурацию и возобновить процесс преобразования следующим образом:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Затем Convert-CcIsoToVhdx создает базовый VM, устанавливает некоторые базовые компоненты, от которых зависит облачный соединитель, а затем Windows обновления. Наконец, он обобъединит виртуальную машину (sysprep) для получения базового VHDX-файла, который будет использоваться виртуальными машинами устройства облачного соединителя. 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Convert-CcIsoToVhdx не принимается конвейерный ввод. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

