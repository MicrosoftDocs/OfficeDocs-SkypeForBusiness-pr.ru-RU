---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Этот Enter-CcUpdate подготавливает сервер Skype для бизнеса Cloud Connector Edition для процесса обновления, вводя его в режим обслуживания. Устройство немедленно останавливает все службы, прерывая текущие вызовы и отклоняет новые вызовы.
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620765"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Этот Enter-CcUpdate подготавливает сервер Skype для бизнеса Cloud Connector Edition для процесса обновления, вводя его в режим обслуживания. Устройство немедленно останавливает все службы, прерывая текущие вызовы и отклоняет новые вызовы.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере устройство готовится к процессу обновления, введите режим обслуживания:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Enter-CcUpdate немедленно остановит все службы, завершающиеся текущими вызовами, и устройство отклоняет все новые вызовы, которые передаются на другие производственные устройства. Необходимо убедиться, что остальные производственные устройства имеют достаточно возможностей для обработки вызовов из устройства, которое вы готовите к обновлению.
  
Режим обслуживания полезен, если в вашем устройстве включено автоматическое обновление, например, и Корпорация Майкрософт выпускает критический hotfix. Режим обслуживания также полезен, если вы решите отключить автоматические обновления, но выполняете обновления вручную на постоянной основе.
  
После установки обновлений устройство можно вернуть в режим производства, заняв Exit-CcUpdate.
  
> [!NOTE]
> Если вы решили вручную обновить устройство Облачного соединителю, его необходимо обновить в течение 60 дней после выпуска следующей версии Microsoft. Корпорация Майкрософт поддерживает ранее выпущенную версию облачного соединиттеля в течение 60 дней после выпуска новой версии 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Enter-CCUpdate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

