---
title: Управление телефонным диалогом в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: Сводка. Узнайте, как управлять телефонным диалогом в Skype для бизнеса Server.
ms.openlocfilehash: 3c6f72d3e2c5e19ef970e7d8e5410dcc9cad2d14
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772065"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Управление телефонным диалогом в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять телефонным диалогом в Skype для бизнеса Server.
  
В этом разделе описывается управление телефонной беседой. Дополнительные сведения о планировании и настройке телефонных телефонных конференций при развертывании см. в дополнительных сведениях: Plan [for dial-in conferencing in Skype для бизнеса Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) and [Configure dial-in conferencing in Skype для бизнеса Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Вы можете выполнять следующие задачи по управлению конференц-конференц-залами с телефонным входом: включить или отключить конференц-конференции, управлять номерами доступа, управлять политиками ПИН-кода для набора номера в конференц-залах, управлять объявлениями о присоединении к конференции и оставлять их, изменять сопоставления ключей для команд DTMF и приветствовать пользователей на конференц-конференциях. 
  
Дополнительные сведения об управлении наборами телефонных планов см. в этой [Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
Дополнительные сведения об использовании PSTN см. в дополнительных сведениях о настройке голосовых политик, записей использования [PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)и маршрутов голосовой Skype для бизнеса .
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Управление телефонным диалогом с помощью панели управления Skype для бизнеса Server

Управление сведениями о телефонных конференцах:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой области навигации щелкните элемент **Конференция**.
    
Управление сведениями о планах набора и использовании PSTN:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **маршрутику голосовой почты**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Управление телефонным диалогом с помощью Skype для бизнеса Server shell

Для управления телефонным диалогом с помощью Skype для бизнеса Server management Shell используйте следующие команды:
  
**Параметры конфигурации dial-in**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Извлекает сведения о том, как Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры многочастотной сигнализации с двойным тоном (DTMF), используемые для телефонных конференцов. Двухтональный многочастотный набор позволяет пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включать и отключать собственный микрофон или блокировать и разблокировать конференцию) с помощью клавиатуры телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе региональных и национальных языков, поддерживаемых для Skype для бизнеса Server конференц-связи. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в организации.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импортирует каталоги конференций Microsoft Office Communications Server 2007 R2 в Skype для бизнеса Server. Это позволяет обеспечить взаимодействие между Skype для бизнеса Server и Office communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Создает новую коллекцию двухтонных многочастотных параметров сигнализации, используемых для телефонных собраний.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию двухтонных многочастотных параметров сигнализации, используемых для телефонных собраний.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Изменяет параметры, определяя Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Изменяет параметры сигналов двухтонального многочастотного набора (DTMF), используемые для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Изменяет существующую абонентскую группу.  <br/> |
   
**Параметры политики ПИН-кода**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках PIN-кодов, используемых в вашей организации. Проверка подлинности ПИН-кода позволяет пользователям получать Skype для бизнеса Server, предоставляя ПИН-код вместо имени пользователя и пароля.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Назначает клиентскую политику персональных идентификационных номеров (PIN-кодов) пользователю или группе пользователей.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Создает новую клиентскую политику персональных идентификационных номеров (PIN-кодов).  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Удаляет указанную политику персонального идентификационного номера (PIN-кода).  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Изменяет одну или несколько существующих политик использования клиентского персонального идентификационного номера (PIN-кода).  <br/> |
