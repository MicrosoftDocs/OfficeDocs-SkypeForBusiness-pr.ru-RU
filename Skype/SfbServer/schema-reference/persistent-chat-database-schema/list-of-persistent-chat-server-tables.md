---
title: Список таблиц сервера сохраняемого чата
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
description: Схема базы данных Persistent Chat состоит из следующих таблиц.
ms.openlocfilehash: e2ce24bb37c3ea4eaee0986f0243033ab4a8a18a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898545"
---
# <a name="list-of-persistent-chat-server-tables"></a>Список таблиц сервера сохраняемого чата
 
Схема базы данных Persistent Chat состоит из следующих таблиц.
  
## <a name="active-directory-sync"></a>Синхронизация с Active Directory

|**Таблица**|**Описание**.|
|:-----|:-----|
|[tblADCookie](tbladcookie.md) <br/> |Содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP). Каждая строка соответствует домене доменных служб Active Directory, отслеживая сервера сохраняемого чата для изменения. (Доменов Active Directory, применяемых для сервера сохраняемого чата, представленные в этой таблице).  <br/> |
|[tblPrincipalMemberDifference](tblprincipalmemberdifference.md) <br/> |Содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации Active Directory и — это один из временных таблиц (а также таблица tblADUpdates), которые используются на первом шаге синхронизации Active Directory.  <br/> Изменения членства, хранятся и обрабатываются, или только для тех групп, которые перечислены в таблице tblPrincipal или, который уже существует члены которых содержатся.  <br/> |
|[tblADUpdates](tbladupdates.md) <br/> |Содержит изменения в доменные службы Active Directory, который еще не были обработаны с последующих этапах синхронизации Active Directory и — это один из временных таблиц (а также в таблице tblPrincipalMemberDifference), которые используются на первом шаге Active Directory Синхронизация.  <br/> Изменения в Active Directory, хранятся и обрабатываются только для тех субъектов, которые перечислены в таблице tblPrincipal.  <br/> |
|[tblPrincipalMembers](tblprincipalmembers.md) <br/> |Содержит сведения о членстве субъектов.  <br/> |
|[tblPrincipalMeta](tblprincipalmeta.md) <br/> |Содержит список субъектов, которых необходимо обновить из Active Directory.  <br/> |
|[tblSkippedAffiliations](tblskippedaffiliations.md) <br/> |Содержит назначения, которые не удалось обновить по какой-либо причине, обычно вследствие ошибок доступа к Active Directory.  <br/> Эта таблица является исключительно в ознакомительных целях. Его содержимое не используется.  <br/> Субъекты, назначения, которые не удалось правильно обновить, сохраняются в таблице tblPrincipalMeta и присваивается могут быть обновлены еще раз.  <br/> |
   
## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Субъекты, назначения, узлы, области и роли

|**Таблица**|**Описание**.|
|:-----|:-----|
|[tblPrincipalType](tblprincipaltype.md) <br/> |Содержит типы субъектов для возможности в таблице tblPrincipal. В этой таблице является статическим. Его настройка во время создания базы данных и не изменяется.  <br/> |
|[tblPrincipal](tblprincipal.md) <br/> |Содержит все субъекты (пользователи, папки, групп и т. п.). Серверов сохраняемого чата обрабатывает это как плоская разнородных списка. Различные столбцы основаны на тип каждого участника.  <br/> Большая часть этих участников, кэшированной копии объектов, хранимых в Active Directory. Создание кэшированную копию в основной таблице эти объекты Active Directory называется подготовки.  <br/> Некоторые субъекты создаются чаще чем другие, а некоторые объекты Active Directory полностью игнорируются.  <br/> |
|[tblPrincipalAffiliations](tblprincipalaffiliations.md) <br/> |Содержит присоединения субъектов, которые описывают членство в группы безопасности Active Directory, контейнеры Active Directory и т. д.  <br/> |
|[tblNode](tblnode.md) <br/> |Содержит узел категории, управление которым осуществляется в панели управления.  <br/> |
|[tblRoleType](tblroletype.md) <br/> |Содержит типы ролей и связанные разрешения наборов. Эта таблица подстановки статического.  <br/> |
|[tblScopePrincipal](tblscopeprincipal.md) <br/> |Содержит области, назначенные узлам.  <br/> |
|[tblPrincipalRole](tblprincipalrole.md) <br/> |Содержит роли, назначенные узлам.  <br/> |
|[tblSiopWhiteList](tblsiopwhitelist.md) <br/> |Содержит зарегистрированные надстройки, которые могут быть связаны с узлами.  <br/> |
|[tblEnumAttribute](tblenumattribute.md) <br/> |Содержит только встроенные «Visibility» и «Behavior» атрибуты, используемые в таблице tblNode.  <br/> |
|[tblEnumValue](tblenumvalue.md) <br/> |Содержит значения, используемые в таблице tblNode атрибутов «Visibility» и «Behavior» жестко.  <br/> |
   
## <a name="invites-chats-and-other-client-support"></a>Приглашения, чаты и другие поддерживаемые клиентом функции

|**Таблица**|**Описание**.|
|:-----|:-----|
|[tblPrincipalInvites](tblprincipalinvites.md) <br/> |Содержит приглашения для всех подготовленных пользователей в системе для всех узлов с включено автоматическое приглашение.  <br/> |
|[tblChat](tblchat.md) <br/> |Содержит все сообщения чата.  <br/> |
|[tblLastInviteId](tbllastinviteid.md) <br/> |Содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.  <br/> |
|[tblLastChatId](tbllastchatid.md) <br/> |Содержит последние Идентификаторы чатов, созданного (и используемый в таблице tblChat) для каждого пользователя.  <br/> |
|[tblPreference](tblpreference.md) <br/> |Содержит пользовательские настройки клиента (используется только для устаревших клиентов).  <br/> |
|[tblFileToken](tblfiletoken.md) <br/> |Содержит временные маркеры для передачи файлов. Каждый раз файл отправлен или загружен, служба Persistent Chat создает маркер, клиент использует для доступа к веб-службе файла хранилища.  <br/> |
   
## <a name="server-support"></a>Поддержка сервера

|**Таблица**|**Описание**.|
|:-----|:-----|
|[tblServerIdentity](tblserveridentity.md) <br/> |Содержит активные серверы в пуле серверов сохраняемого чата.  <br/> |
|[tblAdminLock](tbladminlock.md) <br/> |Содержит блокировку администратора для запуска некоторых команд администратора. Запись версии системы в таблице таблица tblSystemRevision увеличивается после каждого выпуска блокировки.  <br/> |
|[tblSystemRevision](tblsystemrevision.md) <br/> |Содержит номер редакции, используемый (наряду с таблицей tblAdminLock) для обеспечения согласованности на нескольких серверах.  <br/> |
|[tblActivePeers](tblactivepeers.md) <br/> |Содержит текущие peer-to-peer соединения между службами Persistent Chat.  <br/> |
|[tblConfig](tblconfig.md) <br/> |Содержит неподдерживаемые конфигурации сервера сохраняемого чата.  <br/> |
   

