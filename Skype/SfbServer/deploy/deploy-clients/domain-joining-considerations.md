---
title: Вопросы присоединения к домену Системы номеров Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Ознакомьтесь с этой темой, чтобы узнать, как присоединиться к компьютеру устройства skype Room System к вашему домену.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093573"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Вопросы присоединения к домену Системы номеров Skype
 
Ознакомьтесь с этой темой, чтобы узнать, как присоединиться к компьютеру устройства skype Room System к вашему домену.
  
## <a name="domain-joining-considerations"></a>Сведения о присоединении к домену

Вы можете присоединиться к компьютеру устройства Skype Room System к домену Active Directory или оставить его в workgroup. Перед принятием этого решения рассмотрите следующие моменты:
  
- Присоединение домена к компьютеру устройства skype Room System помогает автоматически импортировать частную корневую цепочку сертификатов организации.
    
- Присоединение домена к компьютеру устройства Skype Room System позволяет предоставлять пользователям домена и группам административные права. Таким образом, вам не придется запоминать пароль учетной записи администратора локального уровня компьютера.
    
- При подстройке компьютера-устройства Skype Room System к домену необходимо создать отдельное организационное подразделение (OU), чтобы вы могли предоставлять исключения объектов групповой политики (GPO) в OU, где находятся все объекты системы номеров Skype. При этом создайте машинные объекты в OU перед присоединением к домену компьютера устройства Skype Room System.
    
- Во многих организациях имеются следующие GPOs, которые влияют на функции ПК устройства Skype Room System. Убедитесь, что вы переопределяют или блокируете наследование этих GPOs в OU системы номеров Skype: 
    
  - Периодику сеансов логотипа (автоматическая блокировка)
    
  - Политики управления питанием
    
  - Требуются дополнительные действия проверки подлинности
    
  - Отказ в доступе к локальным дискам
    
  - Запрос пользователей для медленных подключений к сети
    
  - Запуск определенной программы в logon
    
  - Создайте другую учетную запись пользователя домена на всех компьютерах, присоединив к домену.
    
  - Push Windows Update to Skype Room System
    
- Кроме того, вы можете оставить компьютер устройства в группе. Как и для настольного клиента Skype для бизнеса, для этого необходимо вручную импортировать корневую цепочку сертификатов на компьютере устройства Skype Room System. Импорт корневой цепочки сертификатов не требуется, если развертывание Skype для бизнеса использует общедоступный сертификат (например, Entrust, VeriSign и так далее). 
    
Если вы планируете присоединиться к компьютерам системы skype Room System к домену, чтобы избежать случайного присоединения к компьютеру Skype Room System к непреднамеренным OU, который может быть не свободен от GPOs, убедитесь, что вы присоединитесь к правильному OU. Чтобы присоединиться к правильному OU, можно использовать следующий cmdlet из машины Skype Room System и не получать GPOs, которые могут блокировать функции LRS. Свяжитесь с системным администратором или партнером OEM для запуска этих групп:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Даже если вы создаете отдельный OU и блокируете наследование, существуют политики, которые могут вызвать проблемы на более высоком уровне. Групповая политика без параметра Переопределения бьет OU с параметром Наследования политик блока. Дополнительные сведения см. в статье [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.
  
У вас может быть несколько подходов к решению этих проблем. Мы советуем вам проконсультироваться со специалистами Active Directory, чтобы убедиться, что у вас есть соответствующие параметры GPO или, по крайней мере, OU, в котором ранее описанные политики не существуют. Рекомендуется включить службы качества (QoS) для устройств Skype Room System.

## <a name="see-also"></a>См. также
  
[Конфигурация устройств: создание новой или редактирование существующей](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Управление качеством обслуживания](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)