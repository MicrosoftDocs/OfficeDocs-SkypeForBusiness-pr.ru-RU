---
title: Рекомендации по присоединению к домену для системы комнат Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Администратор может узнать о том, как присоединиться к устройству с устройством системы комнат Skype в домене Active Directory, а также о том, как это сделать.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905441"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Рекомендации по присоединению к домену для системы комнат Skype
 
В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
  
## <a name="domain-joining-considerations"></a>Рекомендации по присоединению к домену

Вы можете присоединиться к домену Active Directory с помощью устройства Skype Room System или оставить его в "Workgroup". Consider the following points before making this decision:
  
- Присоединение домена к компьютеру-устройству Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.
- Присоединение домена к компьютеру-устройству Skype Room System позволяет предоставлять пользователям домена и группам права администратора. By doing so, you will not have to remember the local machine level administrator account password.
- Когда вы присоединяете к домену устройство системы комнат Skype, необходимо создать отдельный подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты системы комнат Skype. При этом создавайте объекты компьютера в системе управления объектами, прежде чем присоединяться к устройству системы комнат Skype в домене.
- Во многих организациях есть следующие GOS, которые влияют на функции устройства Скайп-комнатной системы. Переопределять или блокировать наследование этих GGPOs в системе комнат Skype:

  - Время ожидания для сеансов входа (автоматическая блокировка)
  - Политики, связанные с управлением питанием
  - Необходимость дополнительных действий для проверки подлинности
  - Отказ в доступе к локальным дискам
  - Отображение подсказок при низкой скорости сетевого подключения
  - Запуск определенной программы при входе
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
  - Push-обновление Windows до Skype Room System
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как и в клиенте Для настольных систем Microsoft Teams или Skype для бизнеса, вам необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System. Вам не нужно импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, "Доверить", "VeriSign" и другие). 
    
Если вы планируете присоединить компьютеры с комнатами Skype в домене, чтобы избежать случайного присоединения к системным помещениям Skype для непредусмотренного OU, который может быть недоступен для GOS, убедитесь, что вы присоединились к правильному OU. Вы можете использовать следующий cmdlet с компьютера Skype Room System, чтобы присоединиться к правильному OU и не получать GOS, которые могут блокировать функции LRS. Contact your system administrator or OEM partner to run these cmdlet:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если создано отдельное подразделение и наследование заблокировано, некоторые политики могут привести к возникновению проблем на более высоком уровне. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Дополнительные сведения см. в статье ["Сравнение](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) с наследованием политик блокировки" в документации групповой политики.
  
You may have multiple approaches to solving these problems. We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist. Рекомендуется включить качество обслуживания (QoS) для устройств с системой комнат Skype.

## <a name="related-topics"></a>Статьи по теме
  
[Конфигурация устройств: создание новой или редактирование существующей](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
