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
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Администратор может узнать о том, как присоединиться к Skype компьютеру с устройством Room System в домене Active Directory, а также о том, как это сделать.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7956160f57971e48f1f979a7c0a905d760b767bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579603"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Рекомендации по присоединению к домену для системы комнат Skype
 
В этом разделе описывается присоединение к домену ПК с системой комнат Skype.
  
## <a name="domain-joining-considerations"></a>Рекомендации по присоединению к домену

Вы можете присоединиться к устройству Skype Room System к домену Active Directory или оставить его в группе. Consider the following points before making this decision:
  
- Присоединение домена к компьютеру Skype Room System помогает автоматически импортировать цепочку частных корневых сертификатов вашей организации.
- Присоединение домена к компьютеру Skype Room System позволяет предоставлять пользователям домена и группам права администратора. By doing so, you will not have to remember the local machine level administrator account password.
- Когда вы присоединяете к домену устройство Skype Room System, необходимо создать отдельное подразделение, чтобы исключить объект групповой политики (GPO) в подразделении, где находятся все объекты Skype Room System. При этом создавайте машинные объекты в OU, прежде чем присоединяться к Skype устройства Room System к домену.
- Во многих организациях есть следующие GOS, которые влияют на Skype устройством компьютера для помещения. Переопределять или блокировать наследование этих GOS в Skype Room System OU:

  - Время ожидания для сеансов входа (автоматическая блокировка)
  - Политики, связанные с управлением питанием
  - Необходимость дополнительных действий для проверки подлинности
  - Отказ в доступе к локальным дискам
  - Отображение подсказок при низкой скорости сетевого подключения
  - Запуск определенной программы при входе
  - Создание еще одной учетной записи пользователя домена на всех компьютерах, присоединенных к домену
  - Push-Windows обновления для Skype room System
    
- Alternatively, you might decide to leave the appliance PC in the workgroup. Как и в клиенте Microsoft Teams или Skype для бизнеса, необходимо вручную импортировать корневую цепочку сертификатов на компьютере с устройством Skype Room System. Вам не требуется импортировать корневую цепочку сертификатов, если в развертывании используется общедоступный сертификат (например, Заверять, VeriSign и другие). 
    
Если вы планируете присоединиться к домену компьютеры Skype Room System, чтобы предотвратить случайное присоединение компьютера Skype Room System к случайному проекту, который может быть недоступен в GOS, убедитесь, что вы присоединились к правильному OU. Чтобы присоединиться к правильному проекту с Skype Room System, вы можете использовать следующий Skype, но не получать GGPOs, которые могут блокировать функции LRS. Обратитесь к системного администратора или партнеру OEM, чтобы выполнить эти cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если вы создаете отдельное ОО и блокируете наследование, существуют некоторые политики, которые могут вызывать проблемы более высокого уровня. Групповая политика с параметром "Без переопределения" имеет приоритет над подразделением с параметром блокировки наследования политики. Дополнительные сведения см. в [документе Групповая](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) политика без переопределения по сравнению с наследованием блокирования политики.
  
You may have multiple approaches to solving these problems. Мы советуем обратиться к экспертам Active Directory, чтобы убедиться в том, что у вас есть оповеская информация с соответствующими настройками GPO или, по крайней мере, оповеская информация, в которой ранее описанные политики не существуют. Мы советуем обеспечить качество обслуживания (QoS) для Skype система комнат.

## <a name="related-topics"></a>Статьи по теме
  
[Конфигурация устройств: создание новой или редактирование существующей](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)