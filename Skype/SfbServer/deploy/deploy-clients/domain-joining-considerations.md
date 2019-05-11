---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
ms.openlocfilehash: 9e6260ae852d66fd435ce236e28df0c992369eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895189"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Рекомендации по присоединению к домену для системы комнат Skype
 
В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
  
## <a name="domain-joining-considerations"></a>Рекомендации по присоединению к домену

Можно присоединиться к appliance системы комнаты Скайп ПК в домен Active Directory или оставьте его в рабочую группу. Consider the following points before making this decision:
  
- Присоединение домена appliance системы комнаты Скайп ПК позволяет автоматически Импорт цепочки сертификатов частный корневой вашей организации.
    
- Присоединение домена appliance системы комнаты Скайп ПК позволяет предоставить административные права групп и пользователей домена. By doing so, you will not have to remember the local machine level administrator account password.
    
- При подключении устройства системы комнаты Скайп ПК к домену, это необходимо создать отдельные организационному подразделению (OU), таким образом, можно обеспечить исключения для объекта групповой политики (GPO) для Подразделения, в которой размещаются все объекты Скайп комнаты системы компьютера. При этом создание объектов компьютера в Подразделении перед присоединением appliance системы комнаты Скайп ПК к домену.
    
- Многие организации имеют следующие объекты групповой политики, которые могут повлиять на системные комнаты Скайп appliance ПК функции. Убедитесь, что переопределить или блокировка наследования эти объекты групповой политики в Подразделении Скайп комнаты системы: 
    
  - Время ожидания для сеансов входа (автоматическая блокировка)
    
  - Политики, связанные с управлением питанием
    
  - Необходимость дополнительных действий для проверки подлинности
    
  - Отказ в доступе к локальным дискам
    
  - Отображение подсказок при низкой скорости сетевого подключения
    
  - Запуск определенной программы при входе
    
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
    
  - Push-комнаты Скайп системе центра обновления Windows
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как на рабочий стол Скайп для клиента Business этого необходимо вручную Импорт цепочки корневого сертификата на устройстве системы комнаты Скайп ПК. В случае не требуется импортировать цепочки сертификатов корневого, если ваше Скайп по развертыванию использует общедоступный сертификат (например, Entrust VeriSign и т. п.). 
    
Если вы планируете присоединение к домену машины Скайп комнаты системы, во избежание соединение Скайп комнаты системы компьютера случайно to случайных Подразделения, которая не может быть от объектов групповой политики, убедитесь, что присоединиться к правильный Подразделения. Можно использовать следующий командлет с компьютера Скайп комнаты системы для присоединения к правильный подразделения и не получает объекты групповой политики, которые могут блокировать LRS функциональные возможности. Contact your system administrator or OEM partner to run these cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Для получения дополнительных сведений обратитесь к статье, [Не перекрывать по сравнению с блокировать наследование политики](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) в документации по групповой политики.
  
You may have multiple approaches to solving these problems. We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist. Рекомендуется включить качество обслуживания (QoS) для устройств Скайп комнаты системы.

## <a name="see-also"></a>См. также
  
[Конфигурация устройств: создание новой или редактирование существующей](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
