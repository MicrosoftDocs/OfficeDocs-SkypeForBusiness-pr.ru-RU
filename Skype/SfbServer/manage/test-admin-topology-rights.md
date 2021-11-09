---
title: Тестирование прав топологии администратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Проверка прав топологии в Skype для бизнеса Server
ms.openlocfilehash: 6f4eed0271d9dd6d099d19287f7caa37148f6026
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861316"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Тестирование прав топологии администратора в Skype для бизнеса Server

|&nbsp; |&nbsp; |
|--|--|
|Расписание проверки|После первоначального Skype для бизнеса Server развертывания. При необходимости, если возникают проблемы, связанные с разрешениями.|
|Средство тестирования|Windows PowerShell|
|Необходимые разрешения|При локальном запуске с Skype для бизнеса Server службы управления пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.<br/><br/>При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, которая имеет разрешение на Test-CsSetupPermission cmdlet. Чтобы увидеть список всех ролей RBAC, которые могут использовать этот командлет, запустите следующую команду из Windows PowerShell:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Командлеты -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Description

По умолчанию только администраторы домена могут включить топологию Skype для бизнеса Server и внести большие изменения в Skype для бизнеса Server инфраструктуру. Это не будет проблемой до тех пор, пока администраторы домена и Skype для бизнеса Server администраторы одно и то же. Во многих организациях Skype для бизнеса Server администраторы не имеют административных прав на весь домен. По умолчанию это означает, что эти администраторы (определенные как члены группы RTCUniversalServerAdmins) не могут Skype для бизнеса Server топологии. Чтобы дать членам группы RTCUniversalServerAdmins право вносить изменения в топологию, необходимо назначить необходимые разрешения Active Directory с помощью команды [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)
 
Этот Test-CsSetupPermission проверяет, что необходимые разрешения, необходимые для установки Skype для бизнеса Server или одного из его компонентов, настроены в указанном контейнере Active Directory. Если разрешения не назначены, можно запустить Grant-CsSetupPermission, чтобы предоставить членам группы RTCUniversalServerAdmins право на установку и Skype для бизнеса Server.

## <a name="running-the-test"></a>Запуск теста

Чтобы определить, назначены ли разрешения на установку для контейнера Active Directory, позвоните в Test-CsSetupPermission. Укажите отличительное имя проверяемого контейнера. Например, эта команда проверяет разрешения установки на контейнере ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Дополнительные сведения см. в разделе Справка для [cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если Test-CsSetupPermission определяет, что необходимые разрешения уже установлены в контейнере Active Directory, то в этом случае в этот код возвращается значение True:

Верно 

Если разрешения не установлены, Test-CsSetupPermission возвращает значение False. Обратите внимание, что это значение обычно будет заключено во многих предупреждающих сообщениях. Например:

ВНИМАНИЕ. Запись управления доступом (ACE) atl-cs-001\RTCUniversalServerAdmins; Разрешить; ExtendedRight; Нет; Нет; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ВНИМАНИЕ. Записи управления доступом (ACEs) на объекте "CN=Computers,DC=litwareinc,DC=com" не готовы. 

Неверно 

ВНИМАНИЕ. Обработка "Test-CsSetupPermission" завершена с помощью предупреждений. Во время этого запуска были записаны предупреждения "2". 

ВНИМАНИЕ. Подробные результаты можно найти в "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины сбой теста

Хотя существуют редкие исключения, если Test-CsSetupPermission сбой, что обычно означает, что разрешения на установку не назначены для указанного контейнера Active Directory. Эти разрешения могут быть назначены с помощью Grant-CsSetupPermission. Например, эта команда предоставляет разрешения на установку контейнеру Computers в домене litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Дополнительные сведения см. в разделе Справка для [cmdlet Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)