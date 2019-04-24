---
title: Делегирование административного управления Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 64d1b33c7ee41c028d3af7454a131f67de2c9146
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214703"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Делегирование административного управления Скайп для Business Server 

В Скайп для Business Server административные задачи делегируются для пользователей с помощью компонента доступом на основе ролей (RBAC) элемента управления. При установке Скайп для Business Server число роли RBAC создаются автоматически. These roles correspond to universal security groups in Active Directory Domain Services. Например роль RBAC CsHelpDesk соответствует группе CsHelpDesk, найденные в контейнере Users в доменных службах Active Directory. Кроме того каждой роли RBAC связан с набором Скайп для командлетов Business Server Windows PowerShell. Эти командлеты представления задач, которые могут быть выполнены пользователями, которым был назначен данной роли RBAC. Например роль CsHelpDesk была назначена Lock-CsClientPin и UnlockCsClientPin командлетов. Это означает, что пользователи, которым назначена роль CsHelpDesk можно заблокировать и разблокировать ПИН-кодов пользователей. Тем не менее роль CsHelpDesk не был назначен командлет New-CsVoicePolicy. Это означает, что пользователи, которым назначена роль CsHelpDesk не удается создать новые политики голосовой связи.

## <a name="viewing-information-about-rbac-roles"></a>Просмотр сведений о ролях RBAC

Можно получить базовую информацию о вашей роли RBAC, выполнив следующую команду в Скайп для консоли Business Server:

`Get-CsAdminRole`

Имейте в виду, что удостоверение роли RBAC (например, CsVoiceAdministrator) имеет прямую связь в группу безопасности, обнаруженных в контейнере Users в доменных службах Active Directory.

Чтобы просмотреть список командлетов, которые были назначены роли, используйте команду следующего вида:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Назначение пользователю роли RBAC

Чтобы назначить роль RBAC пользователя, необходимо добавить этого пользователя в соответствующую группу безопасности Active Directory. Например необходимо назначить роль CsLocationAdministrator пользователю, необходимо добавить этого пользователя в группу CsLocationAdministrator. Который может выполняться выполните следующую процедуру:

1. Используя учетную запись, которая имеет разрешение на изменение членства группы Active Directory, выполните вход на компьютер, где установлено Active Directory — пользователи и компьютеры.
2. Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, выберите пункт **Администрирование**и выберите пункт **Active Directory — пользователи и компьютеры**.
3. В Active Directory — пользователи и компьютеры разверните имя домена и щелкните контейнер **Users** .
4. Щелкните группу безопасности **CsLocationAdministrator**правой кнопкой мыши и выберите пункт **Свойства**.
5. В диалоговом окне **Свойства** на вкладке **члены** нажмите кнопку **Добавить**.
6. В диалоговом окне **Выбор пользователей, компьютеров, контактов или группы** введите имя пользователя или отображаемое имя пользователя, добавляемого в группу (например, Кен Майер) в поле **Введите имена выбираемых объектов** и нажмите кнопку **ОК**.
7. В диалоговом окне **Свойства** нажмите **кнопку ОК**.

Чтобы убедиться в том, что была назначена роль RBAC, командлет Get-CsAdminRoleAssignment, передав в командлет SamAccountName (имя входа Active Directory) пользователя. Например выполните следующую команду в Скайп оболочки управления Business Server:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
