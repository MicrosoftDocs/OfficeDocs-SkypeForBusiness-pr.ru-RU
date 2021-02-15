---
title: Тестирование прав администратора топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Тестирование прав топологии в Skype для бизнеса Server
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832849"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Тестирование прав администратора топологии в Skype для бизнеса Server

| | |
|--|--|
|Расписание проверки|После начального развертывания Skype для бизнеса Server. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с помощью оболочки управления Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br/><br/>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, которая имеет разрешение на запуск Test-CsSetupPermission управления. Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, в командной Windows PowerShell командной Windows PowerShell следующую команду:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Описание

По умолчанию только администраторы домена могут включить топологию Skype для бизнеса Server и внести существенные изменения в инфраструктуру Skype для бизнеса Server. This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same. Во многих организациях администраторы Skype для бизнеса Server не имеют административных прав на весь домен. По умолчанию это означает, что эти администраторы (определенные как участники группы RTCUniversalServerAdmins) не могут вносить изменения в топологию Skype для бизнеса Server. Чтобы предоставить участникам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью команды [Grant-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)
 
Этот Test-CsSetupPermission проверяет, настроены ли необходимые разрешения для установки Skype для бизнеса Server или одного из его компонентов в указанном контейнере Active Directory. Если разрешения не назначены, можно запустить Grant-CsSetupPermission, чтобы предоставить участникам группы RTCUniversalServerAdmins право на установку и разрешение Skype для бизнеса Server.

## <a name="running-the-test"></a>Запуск теста

Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите Test-CsSetupPermission управления. Укажите различающейся имя проверяемого контейнера. Например, эта команда проверяет разрешения на установку для контейнера ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Дополнительные сведения см. в разделе справки по [cmdlet Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsSetupPermission, что необходимые разрешения уже установлены для контейнера Active Directory, то он возвращает значение True:

Верно 

Если разрешения не за установлены, Test-CsSetupPermission возвращает значение False. Обратите внимание, что это значение обычно заключено во множество предупреждений. Пример:

ПРЕДУПРЕЖДЕНИЕ: запись управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить; ExtendedRight; Нет; Нет; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ПРЕДУПРЕЖДЕНИЕ. Элементы управления доступом (AES) в объекте "CN=Computers,DC=litwareinc,DC=com" не готовы. 

Неверно 

ПРЕДУПРЕЖДЕНИЕ: обработка Test-CsSetupPermission завершена с предупреждениями. Во время этого запуска были записаны предупреждения "2". 

ПРЕДУПРЕЖДЕНИЕ. Подробные результаты можно найти по C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html. 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым мог произойть сбой теста

Хотя существуют редкие исключения, Test-CsSetupPermission не удается, что обычно означает, что разрешения на установку не назначены для указанного контейнера Active Directory. Эти разрешения могут быть назначены с помощью Grant-CsSetupPermission управления. Например, эта команда предоставляет разрешения на установку контейнеру Computers в домене litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Дополнительные сведения см. в разделе справки по [cmdlet Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)
