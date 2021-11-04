---
title: Список таблиц сервера сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Схема базы данных сохраняемого чата состоит из следующих таблиц.
ms.openlocfilehash: e0586776d13a9e958ba30a84e421e4cba92ba12c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763327"
---
# <a name="list-of-persistent-chat-server-tables"></a>Список таблиц сервера сохраняемого чата
 
Схема базы данных сохраняемого чата состоит из следующих таблиц.
  
## <a name="active-directory-sync"></a>Синхронизация Active Directory

|**Table**|**Описание**|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Содержит текущие файлы cookie синхронизации по протоколу LDAP. Каждая строка соответствует домену Active Directory Domain Services, который постоянный сервер чата активно отслеживает изменения. (В этой таблице представлены только домены Active Directory, которые имеют отношение к серверу сохраняемой беседы.)  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Содержит изменения членства в группах (как добавленных, так и удаленных участников), которые еще не обработаны более поздними шагами синхронизации Active Directory и являются одной из временных таблиц (наряду со таблицей tblADUpdates), которая используется на первом этапе синхронизации Active Directory.  <br/> Изменения, внесенные в членство, хранятся и обрабатываются только для тех групп, которые перечислены в таблице tblPrincipal или члены которых содержатся в ней.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Содержит изменения в службах домена Active Directory, которые еще не обработаны более поздними шагами синхронизации Active Directory и являются одной из временных таблиц (наряду со таблицей tblPrincipalMemberDifference), которая используется на первом этапе active Directory Sync.  <br/> Изменения в Active Directory хранятся, обрабатываются или обрабатываются только для директоров, которые уже указаны в таблице tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Содержит сведения о членстве субъектов.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Содержит принципы, которые необходимо обновить из Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Содержит присоединение, которое не удалось обновить по какой-либо причине, как правило, из-за ошибок доступа к Active Directory.  <br/> Эта таблица служит только для информационных целей. Ее содержимое не используется.  <br/> Субъекты, назначения которых не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и могут быть обновлены еще раз.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Субъекты, назначения, узлы, области действия и роли

|**Table**|**Описание**|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Содержит типы субъектов для разделения содержимого таблицы tblPrincipal на категории. Эта таблица является статической. Она настраивается при создании базы данных и больше не изменяется.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Содержит все субъекты (пользователей, папки, группы и т. д.). Стойкий сервер чата обрабатывает это как плоский разнородный список. Каждый столбец соответствует типу субъекта.  <br/> Большинство из этих принципов являются кэшированные копии объектов, хранимых в Active Directory. Создание кэшной копии в основной таблице этих объектов Active Directory называется подготовка.  <br/> Некоторые принципы создаются более агрессивно, чем другие, а некоторые объекты Active Directory вообще игнорируются.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Содержит основные принадлежности, описывая членство в группах безопасности Active Directory, контейнерах Active Directory и так далее.  <br/> |
|[tblNode](tblnode.md) <br/> |Содержит узел категории, как управляется на панели управления.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Содержит типы ролей и связанные с ними наборы разрешений. Эта таблица подстановки является статической.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Содержит области действия, назначенные узлам.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Содержит роли, назначенные узлам.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Содержит зарегистрированные надстройки, которые можно связать с узлами.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Содержит только встроенные атрибуты "Visibility" и "Behavior", используемые в таблице tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Содержит значения атрибутов "Видимость" и "Поведение", используемых в таблице tblNode.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Приглашения, чаты и другие поддерживаемые клиентом функции

|**Table**|**Описание**|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Содержит приглашения для всех подготовленных пользователей в системе для всех узлов, для которых включено автоматическое приглашение.  <br/> |
|[tblChat](tblchat.md) <br/> |Содержит все сообщения чата.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Содержит последний созданный идентификатор приглашения (используемый в таблице tblPrincipalInvites) для каждого пользователя.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Содержит последний созданный идентификатор чата (используемый в таблице tblChat) для каждого пользователя.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Содержит пользовательские настройки клиента (используется только для устаревших клиентов).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Содержит временные маркеры для передачи файлов. Каждый раз, когда файл загружается или загружается, служба сохраняемого чата создает маркер, который клиент использует для доступа к хранилище файлов веб-службы.  <br/> |
   
## <a name="server-support"></a>Поддержка серверов

|**Table**|**Описание**|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Содержит активные серверы в пуле стойких чат-серверов.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Содержит сведения о блокировке выполнения определенных команд администратором. Значение системного счетчика изменений в таблице tblSystemRevision увеличивается на единицу при каждом снятии блокировки.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Содержит номер редакции, используемый для обеспечения  согласованности на нескольких серверах (наряду с таблицей tblAdminLock).  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Содержит текущие одноранговые подключения между службами сохраняемого чата.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Содержит неподтверченную конфигурацию сохраняемой конфигурации chat Server.  <br/> |
   

