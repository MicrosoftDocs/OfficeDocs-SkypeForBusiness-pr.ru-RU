---
title: Тестирование разрешений администратора в Skype для бизнеса Server
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
description: Тестирование разрешений администратора в Skype для бизнеса Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800099"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Тестирование разрешений администратора в Skype для бизнеса Server

| | |
|--|--|
|Расписание проверки|После начального развертывания Skype для бизнеса Server. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с помощью оболочки управления Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br><br/>При запуске с помощью удаленного экземпляра Windows PowerShell пользователю должна быть назначена роль RBAC с разрешением на Test-CsOUPermission управления доступом. Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, в командной Windows PowerShell командной Windows PowerShell следующую команду:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Описание

При установке Skype для бизнеса Server одна из задач, выполняемых программой установки, предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложений и пользователями InetOrg. Если вы отключили наследование разрешений в Active Directory, установка не сможет назначить эти разрешения. В результате члены группы RTCUniversalUserAdmins не смогут управлять объектами Skype для бизнеса Server. Эти права управления будут доступны только администраторам домена. 

Этот Test-CsOUPermission проверяет, установлены ли необходимые разрешения для управления пользователями, компьютерами и другими объектами в контейнере Active Directory. Если эти разрешения не заданы, эту проблему можно устранить с помощью [запускалета Grant-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) 

Обратите вниманиеGrant-CsOUPermission что разрешения можно назначать только членам группы RTCUniversalUserAdmins. Этот cmdlet нельзя использовать для предоставления разрешений произвольному пользователю или группе. Если вы хотите, чтобы разрешения на управление пользователями были у другого пользователя или группы, следует добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Запуск теста

Чтобы проверить, установлены ли разрешения управления для контейнера, запустите Test-CsOUPermission, за которым следует различающийся имя контейнера и тип проверяемого разрешения. Например, эта команда проверяет, установлены ли разрешения пользователя для OU=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Чтобы проверить несколько разрешений с помощью одной команды, заключив каждый тип разрешений в кавычках, разделять эти типы запятой. Например, эта команда проверяет разрешения пользователей, компьютеров и контактов:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Дополнительные сведения см. в разделе [справки по Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если необходимые разрешения уже установлены, Test-CsOUPermission возвращает ответ из одного слова:

Верно

Если необходимые разрешения не задаются, Test-CsOUPermission возвращает значение False. Возможно, вам придется найти это значение в течение времени. Как правило, он внедряется в несколько сопутствующих предупреждений. Например:

ПРЕДУПРЕЖДЕНИЕ: запись управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Потомки; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

ПРЕДУПРЕЖДЕНИЕ. Элементы управления доступом (AES) в объекте "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" не готовы. 

False 

ПРЕДУПРЕЖДЕНИЕ: обработка Test-CsOUPermission завершена с предупреждениями. Во время этого запуска были записаны предупреждения "2". 

ПРЕДУПРЕЖДЕНИЕ. Подробные результаты можно найти по C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html. 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым мог произойть сбой теста

Если Test-CsOUPermission происходит сбой, это обычно означает, что указанное разрешение не было назначено группе RTCUniversalUserAdmins. Эту проблему можно устранить и назначить необходимые разрешения с помощью Grant-CsOUPermission управления. Например, эта команда предоставляет группе RTCUniversalUserAdmins разрешения для пользователей, контактов и inetOrgPersons:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Дополнительные сведения см. в разделе [справки по Test-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)
