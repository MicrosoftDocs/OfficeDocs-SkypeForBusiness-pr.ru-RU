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
description: Администратор может узнать, как присоединиться к компьютеру с устройством Skype Room System в домен Active Directory, а также о том, как это сделать.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117557"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Рекомендации по присоединению к домену для системы комнат Skype
 
В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
  
## <a name="domain-joining-considerations"></a>Рекомендации по присоединению к домену

Вы можете присоединиться к Skype компьютера-устройства Room System к домену Active Directory или оставить его в группе. Consider the following points before making this decision:
  
- Присоединение домена к компьютеру с устройством Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.
- Присоединение домена к компьютеру Skype Room System позволяет предоставлять пользователям домена и группам права администратора. By doing so, you will not have to remember the local machine level administrator account password.
- Когда вы присоединяете к домену устройство Skype Room System, необходимо создать отдельное подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты Skype Room System. При этом создавайте объекты в ОУ, прежде чем присоединяться к Skype устройства Room System к домену.
- Во многих организациях есть следующие GOS, которые влияют на Skype устройства для компьютера с комнатами. Переопределять или блокировать наследование этих GOS в Skype Room System OU:

  - Время ожидания для сеансов входа (автоматическая блокировка)
  - Политики, связанные с управлением питанием
  - Необходимость дополнительных действий для проверки подлинности
  - Отказ в доступе к локальным дискам
  - Отображение подсказок при низкой скорости сетевого подключения
  - Запуск определенной программы при входе
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
  - Push-Windows обновления для Skype комнаты
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как и в клиенте Microsoft Teams или Skype для бизнеса, необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System. Вам не нужно импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, Заверять, VeriSign и другие). 
    
Если вы планируете присоединиться к домену компьютеры Skype Room System, чтобы избежать случайного присоединения компьютера Skype Room System к случайному агенту, который может быть недоступен в GOS, убедитесь, что вы присоединились к правильному OU. Вы можете использовать следующий Skype-компьютер с системой комнат, чтобы присоединиться к правильному проекту и не получать GGPOs, которые могут блокировать функции LRS. Обратитесь к системного администратора или партнеру OEM, чтобы выполнить эти cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если вы создаете отдельное ОО и блокируете наследование, существуют некоторые политики, которые могут вызывать проблемы более высокого уровня. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Дополнительные сведения см. в [документе Групповая](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) политика без переопределения по сравнению с наследованием блокирования политики.
  
You may have multiple approaches to solving these problems. Мы советуем обратиться к экспертам Active Directory, чтобы убедиться, что у вас есть ОО, у которого есть соответствующие параметры GPO, или по крайней мере один из них, в котором ранее описанные политики не существуют. Мы советуем обеспечить качество обслуживания (QoS) для Skype система комнат.

## <a name="related-topics"></a>Статьи по теме
  
[Конфигурация устройств: создание новой или редактирование существующей](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)