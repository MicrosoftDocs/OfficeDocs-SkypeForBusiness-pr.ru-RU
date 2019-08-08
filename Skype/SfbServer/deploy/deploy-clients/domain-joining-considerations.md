---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
ms.openlocfilehash: 2d2af20173708e199c1de5a205218d3295e7e0d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234387"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Рекомендации по присоединению к домену для системы комнат Skype
 
В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
  
## <a name="domain-joining-considerations"></a>Рекомендации по присоединению к домену

Вы можете присоединиться к компьютеру управляющего устройства Skype Rooms в домен Active Directory или оставить его в Рабочей группе. Consider the following points before making this decision:
  
- Домен: присоединение к компьютеру управляющего устройства в системе комнат Skype поможет вам импортировать цепочку сертификатов частной корневой папки организации автоматически.
    
- Domain (подключение к домену). присоединение к компьютеру управляющего устройства из комнаты Skype позволяет предоставить пользователям домена и группам права администратора. By doing so, you will not have to remember the local machine level administrator account password.
    
- Когда вы присоединяетесь к домену системное устройство для помещения в Skype на компьютер, необходимо создать отдельное подразделение (OU), чтобы вы могли предоставлять исключения объектов групповой политики (GPO) для подразделения, где находятся все объекты компьютера, на котором установлена система Skype для комнаты. После этого создайте объекты компьютера в подразделении, прежде чем присоединиться к домену с помощью устройства управления системой комнаты для помещения Skype на компьютер.
    
- Во многих организациях есть следующие объекты групповой политики, которые влияют на функции ПК в системе управления комнатой Skype. Убедитесь, что вы переопределяете или блокируете наследование этих GPO в подразделении системы помещения в Skype. 
    
  - Время ожидания для сеансов входа (автоматическая блокировка)
    
  - Политики, связанные с управлением питанием
    
  - Необходимость дополнительных действий для проверки подлинности
    
  - Отказ в доступе к локальным дискам
    
  - Отображение подсказок при низкой скорости сетевого подключения
    
  - Запуск определенной программы при входе
    
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
    
  - Принудительное обновление Windows для системы помещения в Skype
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как и в клиенте Skype для бизнеса для настольных компьютеров, для этого требуется вручную импортировать цепочку корневых сертификатов на устройстве с устройством системы комнатной помощи Skype. Если развертывание Skype для бизнеса использует общедоступный сертификат (например, Ентруст, VeriSign и т. д.), вам не нужно импортировать корневую цепочку сертификатов. 
    
Если вы планируете присоединиться к домену с системными машинами Skype, не присоединяясь к системным машинам Skype на непреднамеренном подразделении, не подключаясь к ним, убедитесь, что вы присоединитесь к нужному подразделению. Вы можете использовать следующий командлет с компьютера, на котором есть система для помещения Skype, чтобы присоединиться в подходящую подразделении и не получал ни одной политики, которая может блокировать функцию ЛРС. Contact your system administrator or OEM partner to run these cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Дополнительные сведения можно найти в статье " [не перекрывать" в соответствии с блокированием наследования политик](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) в документации по групповой политике.
  
You may have multiple approaches to solving these problems. We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist. Рекомендуется включить качество обслуживания (QoS) для системных устройств Skype для комнаты.

## <a name="see-also"></a>См. также
  
[Конфигурация устройств: создание новой или редактирование существующей](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
