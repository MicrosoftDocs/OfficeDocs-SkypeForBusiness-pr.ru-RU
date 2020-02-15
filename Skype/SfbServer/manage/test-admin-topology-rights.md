---
title: Тестирование прав топологии администратора в Skype для бизнеса Server
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
description: Проверка прав на топологию в Skype для бизнеса Server
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030152"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Тестирование прав топологии администратора в Skype для бизнеса Server

| | |
|--|--|
|Расписание проверки|После первоначального развертывания Skype для бизнеса Server. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с помощью командной консоли Skype для бизнеса Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br/><br/>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsSetupPermission. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:<br/><br/>Get – CsAdminRole \| Where – Object {$ _. Командлеты-ПОИСКПОЗ "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Описание

По умолчанию только администраторы домена могут включать топологию сервера Skype для бизнеса Server и вносить значительные изменения в инфраструктуру Skype для бизнеса Server. Это не проблема, так как Администраторы домена и администраторы Skype для бизнеса Server относятся к одному и тому же. Во многих организациях администраторы Skype для бизнеса Server не хранят права администратора для всего домена. По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут выполнять изменения топологии Skype для бизнеса Server. Чтобы предоставить членам группы RTCUniversalServerAdmins право на внесение изменений в топологию, необходимо назначить необходимые разрешения Active Directory с помощью командлета [Grant – CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .
 
Командлет Test-CsSetupPermission проверяет, настроены ли необходимые разрешения, необходимые для установки Skype для бизнеса Server или одного из его компонентов, в указанном контейнере Active Directory. Если разрешения не назначены, можно запустить командлет Grant-CsSetupPermission, чтобы предоставить членам группы RTCUniversalServerAdmins право на установку и включение Skype для бизнеса Server.

## <a name="running-the-test"></a>Выполнение теста

Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, вызовите командлет Test-CsSetupPermission. Укажите различающееся имя контейнера, который необходимо проверить. Например, эта команда проверяет разрешения программы установки для контейнера OU = Кссерверс, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsSetupPermission определяет, что необходимые разрешения для контейнера Active Directory уже установлены, командлет вернет значение true:

Верно 

Если разрешения не заданы, Test-CsSetupPermission будет возвращать значение false. Обратите внимание, что это значение, как правило, будет заключено во множество предупреждающих сообщений. Пример:

Предупреждение: элемент управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить Екстендедригхт; Видим Видим 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

Предупреждение: записи управления доступом (ACE) для объекта "CN = Computers, DC = litwareinc, DC = com" не готовы. 

False 

Предупреждение: "Test-CsSetupPermission" обработка завершена с предупреждениями. во время этого запуска было записано предупреждение 2. 

Предупреждение: подробные результаты можно найти по адресу "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Несмотря на то, что в Test-CsSetupPermission возникает редкие исключения, которые обычно означают, что разрешения программы установки для указанного контейнера Active Directory не назначены. Эти разрешения могут быть назначены с помощью командлета Grant – CsSetupPermission. Например, эта команда предоставляет разрешения на установку контейнера Computers в домене litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .
