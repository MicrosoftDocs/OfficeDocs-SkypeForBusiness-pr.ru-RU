---
title: Тестирование разрешений администратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Проверка разрешений администратора в Skype для бизнеса Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030162"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Тестирование разрешений администратора в Skype для бизнеса Server

| | |
|--|--|
|Расписание проверки|После первоначального развертывания Skype для бизнеса Server. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с помощью командной консоли Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br><br/>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsOUPermission. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:<br/><br/>Get – CsAdminRole \| Where – Object {$ _. Командлеты-ПОИСКПОЗ "Test-CsOUPermission"}|
|||

## <a name="description"></a>Описание

При установке Skype для бизнеса Server одна из задач, которая выполнялась программой установки, предоставляет группе RTCUniversalUserAdmins разрешения Active Directory, необходимые для управления пользователями, компьютерами, контактами, контактами приложений и Инеторг. Person. Если вы отключили наследование разрешений в Active Directory, программа установки не сможет назначить эти разрешения. В результате участники группы RTCUniversalUserAdmins не смогут управлять сущностями Skype для бизнеса Server. Эти привилегии управления будут доступны только администраторам домена. 

Командлет Test-CsOUPermission проверяет, что для контейнера Active Directory установлены необходимые разрешения, необходимые для управления пользователями, компьютерами и другими объектами. Если эти разрешения не заданы, можно устранить эту проблему, выполнив [командлет Grant – CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission). 

Обратите внимание, что Grant – CsOUPermission может назначать разрешения только членам группы RTCUniversalUserAdmins. Вы не можете использовать этот командлет для предоставления разрешений произвольному пользователю или группе. Если вы хотите, чтобы другой пользователь или группа применялись к разрешениям управления пользователями, необходимо добавить этого пользователя (или группу) в группу RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Выполнение теста

Чтобы проверить, установлены ли для контейнера разрешения на управление, запустите командлет Test-CsOUPermission, а затем различающееся имя контейнера и тип проверяемых разрешений. Например, эта команда проверяет, установлены ли разрешения пользователя для подразделения OU = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Чтобы проверить несколько разрешений с помощью одной команды, заключите каждый тип разрешения в кавычки, а затем разделите эти типы с помощью запятых. Например, одна команда проверяет разрешения пользователя, компьютера и контакта:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Для получения дополнительных сведений обратитесь к [разделу "Справка" для командлета Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если необходимые разрешения уже заданы, Test-CsOUPermission возвратит ответ из одного слова:

Верно

Если необходимые разрешения не заданы, Test-CsOUPermission будет возвращать значение false. Вам может потребоваться найти это значение в течение некоторого времени. Как правило, она обычно внедряется в несколько соответствующих предупреждений. Пример:

Предупреждение: элемент управления доступом (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; разрешить Реадпроперти; Контаинеринхерит; Потомки bf967aba-0de6-11d0-00aa003049e2; d819615a — 3b9b – 4738 — b47e – f1bd8ee3aea4 

Предупреждение: записи управления доступом (ACE) для объекта "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" не готовы. 

False 

Предупреждение: "Test-CsOUPermission" обработка завершена с предупреждениями. во время этого запуска было записано предупреждение 2. 

Предупреждение: подробные результаты можно найти по адресу "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если Test-CsOUPermission завершается с ошибкой, обычно это означает, что указанное разрешение не было назначено группе RTCUniversalUserAdmins. Эту проблему можно решить и назначить необходимые разрешения с помощью командлета Grant – CsOUPermission. Например, эта команда предоставляет разрешения OU для пользователей, контактов и Инеторгперсонс группе RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Для получения дополнительных сведений обратитесь к [разделу "Справка" для командлета Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
