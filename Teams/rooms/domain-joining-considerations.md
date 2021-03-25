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

Вы можете присоединиться к домену Active Directory с помощью устройства Skype Room System или оставить его в "Workgroup". Consider the following points before making this decision:
  
- Присоединение домена к компьютеру с устройством Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.
- Присоединение домена к компьютеру-устройству Skype Room System позволяет предоставлять пользователям домена и группам права администратора. By doing so, you will not have to remember the local machine level administrator account password.
- Когда вы присоединяете к домену устройство системы комнат Skype, необходимо создать отдельный подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты системы комнат Skype. При этом создавайте объекты компьютера в системе управления объектами, прежде чем присоединяться к устройству системы комнат Skype в домене.
- Во многих организациях есть следующие GOS, которые влияют на функции устройства Скайп-комнатной системы. Переопределять или блокировать наследование этих GGPOs в системе комнат Skype:

  - Время ожидания для сеансов входа (автоматическая блокировка)
  - Политики управления питанием
  - Необходимость дополнительных действий для проверки подлинности
  - Отказ в доступе к локальным дискам
  - Отображение подсказок при низкой скорости сетевого подключения
  - Запуск определенной программы при входе
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
  - Push-обновление Windows до Skype Room System
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как и в клиенте для настольных компьютеров Microsoft Teams или Skype для бизнеса, вам необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System. Вам не нужно импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, Доверенный, VeriSign и другие). 
    
Если вы планируете присоединить компьютеры с комнатами Skype в домене, чтобы избежать случайного присоединения к системным помещениям Skype для непредусмотренного OU, который может быть недоступен для GOS, убедитесь, что вы присоединились к правильному OU. Вы можете использовать следующий cmdlet с компьютера Skype Room System, чтобы присоединиться к правильному OU и не получать GOS, которые могут блокировать функции LRS. Обратитесь к системного администратора или партнеру OEM, чтобы выполнить эти cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если вы создадим отдельный отдел и заблокировали наследование, существуют некоторые политики, которые могут вызывать проблемы более высокого уровня. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Дополнительные сведения [](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) см. в документации групповой политики "Нет переопределения по сравнению с наследованием блокировки политики".
  
You may have multiple approaches to solving these problems. Мы советуем обратиться к экспертам Active Directory, чтобы убедиться, что у вас есть соответствующие параметры для GPO или по крайней мере один из них, в котором ранее описанные политики не существуют. Мы рекомендуем обеспечить качество обслуживания (QoS) для устройств с системой комнат Skype.

## <a name="related-topics"></a>Статьи по теме
  
[Конфигурация устройств: создание новой или редактирование существующей](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)