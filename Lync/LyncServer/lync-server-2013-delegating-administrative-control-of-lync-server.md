---
title: 'Lync Server 2013: делегирование административного управления Lync Server'
description: 'Lync Server 2013: делегирование административного управления Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8d3710af2d194a5aa4ebdd7291be2ee58176507
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567495"
---
# <a name="delegating-administrative-control-of-lync-server-2013"></a>Делегирование административного управления Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

В Lync Server 2013 административные задачи делегируются пользователям с помощью новой функции управления доступом на основе ролей (RBAC). При установке Lync Server создаются некоторые роли RBAC. Эти роли соответствуют универсальным группам безопасности в доменных службах Active Directory. Например, роль RBAC CsHelpDesk соответствует группе CsHelpDesk, находящуюся в контейнере "Пользователи" в доменных службах Active Directory. Кроме того, каждая роль RBAC связана с набором командлетов Windows PowerShell для Lync Server. Эти командлеты представляют задачи, которые могут выполнять пользователи, которым назначена данная роль RBAC. Например, для роли CsHelpDesk были назначены командлеты Lock-CsClientPin и Унлоккксклиентпин. Это означает, что пользователи, которым назначена роль CsHelpDesk, могут блокировать и разблокировать номера ПИН-кодов пользователей. Однако роли CsHelpDesk не назначен командлет New-CsVoicePolicy. Это означает, что пользователи, которым назначена роль CsHelpDesk, не могут создавать новые политики голосовой связи.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Просмотр сведений о ролях RBAC

Вы можете получить основные сведения о ролях RBAC, выполнив следующую команду в командной консоли Lync Server:

    Get-CsAdminRole

Имейте в виду, что идентификатор роли RBAC (например, CsVoiceAdministrator) имеет прямое сопоставление для группы безопасности, обнаруженной в контейнере "Пользователи" в доменных службах Active Directory.

Чтобы просмотреть список командлетов, которые были назначены роли, используйте команду, аналогичную приведенной ниже:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Назначение роли RBAC пользователю

Чтобы назначить роль RBAC пользователю, необходимо добавить этого пользователя в соответствующую группу безопасности Active Directory. Например, чтобы назначить роль CsLocationAdministrator пользователю, его нужно добавить в группу CsLocationAdministrator. Это можно сделать посредством следующей процедуры:

**Назначение пользователя в группу безопасности**

1.  Используя учетную запись с разрешением на изменение членства группы Active Directory, выполните вход на компьютер, где был установлен компонент «Пользователи и компьютеры Active Directory».

2.  Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Пользователи и компьютеры Active Directory**.

3.  В окне «Пользователи и компьютеры Active Directory» разверните имя своего домена и щелкните контейнер **Users**.

4.  Щелкните группу безопасности **CsLocationAdministrator** правой кнопкой мыши и выберите **Свойства**.

5.  В диалоговом окне **Свойства** на вкладке **Члены** нажмите кнопку **Добавить**.

6.  В диалоговом окне **Выбор: Пользователи, Компьютеры, Контакты или Группы** введите имя пользователя или отображаемое имя для пользователя, добавляемого в группу, (например, **Ken Myer**) в поле **Введите имена выбираемых объектов** и нажмите кнопку **ОК**.

7.  В диалоговом окне **Свойства** нажмите кнопку **ОК**.

Чтобы убедиться, что роль управления доступом на основе ролей была назначена, используйте командлет [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment), передавая в него SamAccountName (имя для входа Active Directory) пользователя. Например, выполните следующую команду в командной консоли Lync Server:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

