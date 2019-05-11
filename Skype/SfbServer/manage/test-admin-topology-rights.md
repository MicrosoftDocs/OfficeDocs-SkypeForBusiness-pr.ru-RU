---
title: Проверка топологии права администратора в Скайп Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Проверка топологии правами в Скайп для Business Server
ms.openlocfilehash: 239c35eba451166f4e9fb5755535cf15999cdaea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910370"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Проверка топологии права администратора в Скайп Business Server

| | |
|--|--|
|Расписание проверки|После первоначальной Скайп для развертывания Business Server. При необходимости в случае возникновения проблем, связанных с разрешением.|
|Средства тестирования|Windows PowerShell|
|Требуемые разрешения|При запуске локально с помощью Скайп для консоли Business Server, пользователи должны быть членами группы RTCUniversalServerAdmins безопасности.<br/><br/>При запуске с помощью удаленной оболочки Windows PowerShell, пользователям необходимо назначить роль RBAC, которая имеет разрешение на запуск командлета Test-CsSetupPermission. Чтобы просмотреть список всех ролей RBAC, можно с помощью этого командлета, выполните следующую команду в командной строке Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Командлеты-match «Test-CsSetupPermission»}|
|||

## <a name="description"></a>Описание

По умолчанию только администратор домена можно включить Скайп для топологии Business Server и вносить большие изменения в Скайп для инфраструктуры Business Server. Это не может быть проблема при условии, что администраторы домена и вашей Скайп для администраторов Business Server являются одной и той же. Во многих организациях Скайп для администраторов Business Server не содержат права администратора для всего домена. По умолчанию, это означает, что эти Администраторы (определен как члены группы RTCUniversalServerAdmins) не сможет выполнить Скайп для изменения топологии Business Server. Чтобы предоставить членам группы RTCUniversalServerAdmins вправо для увеличения изменения топологии, необходимо назначить требуемые разрешения Active Directory с помощью командлета [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
Командлет Test-CsSetupPermission проверяет, что в указанный контейнер Active Directory настроены необходимые разрешения, необходимые для установки Скайп для Business Server или один из его компонентов. Если не назначены разрешения, затем можно запустить командлет Grant-CsSetupPermission, чтобы предоставить право установить и включить Скайп для Business Server члены группы RTCUniversalServerAdmins.

## <a name="running-the-test"></a>Тест

Чтобы определить, является ли разрешений на установку назначены для контейнера Active Directory, вызовите командлет Test-CsSetupPermission. Укажите различающееся имя контейнера для проверки. К примеру, эта команда проверяет разрешений на установку на контейнер ou = CsServers, dc = litwareinc, dc = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Для получения дополнительных сведений см раздел справки для командлета [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Определение успешное или неудачное

Если Test-CsSetupPermission определяет, что уже были установлены необходимые разрешения для контейнера Active Directory командлет возвращает значение True:

True 

Если разрешения не заданы, Test-CsSetupPermission возвращает значение False. Обратите внимание на то, что это значение обычно заключаться в много предупреждений. Например:

Предупреждение: Доступ управления доступом atl-cs-001\RTCUniversalServerAdmins; Разрешить; ExtendedRight; None; None; 1131f6aa-9c07-11D1-f79f-00C04FC2DCD2 

Предупреждение: Записи управления доступом (ACE) на объекте «CN = компьютеров, DC = litwareinc, DC = com» еще не готово. 

False 

Предупреждение: «Test-CsSetupPermission» обработка выполнена с предупреждениями. «2» предупреждений, зарегистрированных во время выполнения. 

Предупреждение: Подробные результаты, можно найти в «C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html». 

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, почему не удалось теста

Несмотря на то, что существуют исключения, если Test-CsSetupPermission происходит сбой, который обычно означает, что разрешения на установку не назначаются в указанный контейнер Active Directory. Эти разрешения можно назначить с помощью командлета Grant-CsSetupPermission. Например эта команда предоставляют права настройки в контейнер компьютеров в домене litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Для получения дополнительных сведений см раздел справки для командлета [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
