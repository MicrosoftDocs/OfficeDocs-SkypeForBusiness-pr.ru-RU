---
title: Тестирование разрешения администратора в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Проверка разрешений администратора в Скайп для Business Server
ms.openlocfilehash: 3f3f649ea01f974cf0462cabb7784bedc7a6df4f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214717"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Тестирование разрешения администратора в Скайп для Business Server

| | |
|--|--|
|Расписание проверки|После первоначальной Скайп для развертывания Business Server. При необходимости в случае возникновения проблем, связанных с разрешением.|
|Средства тестирования|Windows PowerShell|
|Требуемые разрешения|При запуске локально с помощью Скайп для консоли Business Server, пользователи должны быть членами группы RTCUniversalServerAdmins безопасности.<br><br/>При запуске с помощью удаленной оболочки Windows PowerShell, пользователям необходимо назначить роль RBAC, которая имеет разрешение на запуск командлета Test-CsOUPermission. Чтобы просмотреть список всех ролей RBAC, можно с помощью этого командлета, выполните следующую команду в командной строке Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Командлеты-match «Test-CsOUPermission»}|
|||

## <a name="description"></a>Описание

При установке Скайп для Business Server одной из задач, выполняемого программой установки предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, которые требуются для управления пользователями, компьютеров, контактов, контактов приложения и InetOrg лица. Если вы отключили наследование разрешений в Active Directory, программа установки не сможет назначать разрешения. В результате члены группы RTCUniversalUserAdmins не сможет управлять Скайп для сущностей Business Server. Эти права управления доступна только для администраторов домена. 

Командлет Test-CsOUPermission проверяет, что для контейнера Active Directory установлены требуемые разрешения, необходимые для управления пользователями, компьютеры и другие объекты. Если эти разрешения не заданы, можно устранить эту проблему, выполнив [командлет Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Обратите внимание на то, что Grant-CsOUPermission могут быть назначены только разрешений членам группы RTCUniversalUserAdmins. Этот командлет нельзя использовать для предоставления разрешений на произвольного пользователя или группы. Если необходимо иметь разрешения на управление пользователями другого пользователя или группы, следует добавить в группу RTCUniversalUserAdmins этого пользователя (или группы). 


## <a name="running-the-test"></a>Тест

Чтобы убедиться, что установлены разрешения управления в контейнере, запустите командлет Test-CsOUPermission, затем по различающееся имя контейнера и по типу разрешения, которые проверяются. Например, эта команда проверяет установил ли разрешения пользователя на подразделение OU = Redmond, dc = litwareinc, dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения, заключенной в кавычки, а затем разделяются запятыми этих типов. Например один проверяется пользователей и компьютеров контакт разрешения:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Для получения дополнительных сведений см [раздел справки для командлета Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Определение успешное или неудачное

Если уже были установлены соответствующие разрешения, Test-CsOUPermission возвращает ответа одного слова:

True

Если заданы соответствующие разрешения, Test-CsOUPermission возвращает значение False. Может потребоваться поиск некоторое время найти это значение. Оно обычно внедряться в несколько сопутствующий предупреждения. Например:

Предупреждение: доступ к управления доступом atl-cs-001\RTCUniversalUserReadOnlyGroup; Разрешить; ReadProperty; ContainerInherit; Потомки; 0 bf967aba-0de6 - 11d-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Предупреждение: Записи управления доступом (ACE) на объекте «OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com» еще не готово. 

False 

Предупреждение: «Test-CsOUPermission» обработка выполнена с предупреждениями. «2» предупреждений, зарегистрированных во время выполнения. 

Предупреждение: Подробные результаты, можно найти в «C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html». 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, почему не удалось теста

Если Test-CsOUPermission не удается, это обычно означает, что указанное разрешение не был назначен группе RTCUniversalUserAdmins. Можно устранить неполадки и назначить требуемые разрешения с помощью командлета Grant-CsOUPermission. Например эта команда предоставляет разрешения Подразделения для пользователей, контактов и inetOrgPersons в группу RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Для получения дополнительных сведений см [раздел справки для командлета Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
