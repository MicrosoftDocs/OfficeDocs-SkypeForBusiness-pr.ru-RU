---
title: Тестирование разрешений администратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Проверка разрешений администратора в Skype для бизнеса Server
ms.openlocfilehash: 48ffbe6863a85ecaa98cb526c16819f3d520def0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391121"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Тестирование разрешений администратора в Skype для бизнеса Server

|&nbsp; |&nbsp; |
|--|--|
|Расписание проверки|После первоначального Skype для бизнеса Server развертывания. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с Skype для бизнеса Server службы управления пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br><br/>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, которая имеет разрешение на Test-CsOUPermission cmdlet. Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, запустите следующую команду из Windows PowerShell:<br/><br/>\| Get-CsAdminRole Where-Object {$_. Командлеты -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Описание

При установке Skype для бизнеса Server одна из задач, выполняемых программой Установки, предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложений и пользователями InetOrg. Если у вас отключено наследование разрешений в Active Directory, установка не сможет назначить эти разрешения. В результате члены группы RTCUniversalUserAdmins не смогут управлять Skype для бизнеса Server сущностями. Эти привилегии управления будут доступны только администраторам доменов. 

Этот Test-CsOUPermission проверяет, что необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами, устанавливаются в контейнере Active Directory. Если эти разрешения не заданы, эту проблему можно решить с помощью [комлета Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission). 

Обратите внимание, Grant-CsOUPermission могут назначать разрешения только членам группы RTCUniversalUserAdmins. Этот кодлет нельзя использовать для предоставления разрешений произвольному пользователю или группе. Если вы хотите, чтобы у другого пользователя или группы были разрешения на управление пользователями, следует добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Запуск теста

Чтобы убедиться, что на контейнере установлены разрешения управления, запустите Test-CsOUPermission, за которым следует отличительное имя контейнера и тип разрешений, которые вы проверяете. Например, эта команда проверяет, задаются ли разрешения пользователей на OU=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Чтобы проверить несколько разрешений с помощью одной команды, заключив каждый тип разрешения, заключенный в кавычках, затем разделять эти типы с помощью запятых. Например, эта команда проверяет разрешения пользователя, компьютера и контактов:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Дополнительные сведения см. в разделе [справка для Test-CsOUPermission.](/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если необходимые разрешения уже установлены, Test-CsOUPermission возвращает одно слово ответа:

Верно

Если необходимые разрешения не установлены, Test-CsOUPermission возвращает значение False. Возможно, вам придется найти момент, чтобы найти это значение. Как правило, он будет встроен в несколько сопутствующих предупреждений. Например:

ВНИМАНИЕ: запись управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; разрешить; ReadProperty; ContainerInherit; Потомки; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

ВНИМАНИЕ. Записи управления доступом (ACEs) на объекте "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" не готовы. 

Неверно 

ВНИМАНИЕ. Обработка "Test-CsOUPermission" завершена с помощью предупреждений. Во время этого запуска были записаны предупреждения "2". 

ВНИМАНИЕ. Подробные результаты можно найти в "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины сбой теста

Если Test-CsOUPermission сбой, это обычно означает, что указанное разрешение не было назначено группе RTCUniversalUserAdmins. Вы можете разрешить эту проблему и назначить необходимые разрешения с помощью Grant-CsOUPermission. Например, эта команда предоставляет разрешения OU для пользователей, контактов и inetOrgPersons группе RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Дополнительные сведения см. в разделе [справка для Test-CsOUPermission.](/powershell/module/skype/test-csoupermission)