---
title: Управлениеконференцией с помощью телефонного номера в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: Сводка. Узнайте, как управлять телефонной комконференцией в Skype для бизнеса Server.
ms.openlocfilehash: 2674db010939f7b544ee296aea28739ecc7b806d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828159"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Управлениеконференцией с помощью телефонного номера в Skype для бизнеса Server
 
**Сводка:** Learn how to manage dial-in conferencing in Skype for Business Server.
  
В этом разделе описывается, как управлять телефонной комконференцией. For more information about how to plan and configure dial-in conferencing at deployment, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) and [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Для управления конференц-конференц-конференц-залом с телефонным присоединением можно выполнить следующие задачи: включить или отключить конференц-конференцию с телефонным присоединением, управлять номерами доступа, управлять политиками ПИН-кодов для конференц-конференций с телефонным присоединением, управлять объявлениями о присоединении к конференции и выходе из нее, изменять сопоставления клавиш для команд DTMF и приветствовать пользователей конференц-залом с телефонным присоединением. 
  
Дополнительные сведения об управлении планами телефонных номеров см. в сведениях о создании или изменении телефонной программы [в Skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
Дополнительные сведения об использовании ЗВОНКОВ см. в подстройке "Настройка политик голосовой почты", записей использования ЗВОНКОВ и маршрутов голосовых вызовов [в Skype для бизнеса.](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Manage dial-in conferencing by using Skype for Business Server Control Panel

Для управления сведениями о телефонной комконференции:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните элемент **Конференция**.
    
Для управления сведениями о наборах номеров и использовании PSTN:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **маршрутику голосовой почты.**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Manage dial-in conferencing by using Skype for Business Server Management Shell

Для управления телефонной комконференцией с помощью skype для бизнеса Server Management Shell используйте следующие команды:
  
**Параметры конфигурации телефонного номера**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Извлекает сведения о том, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры сигналов двухтонального многочастотного набора (DTMF), используемые для телефонной связи. Двухтональный многочастотный набор позволяет пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включать и отключать собственный микрофон или блокировать и разблокировать конференцию) с помощью клавиатуры телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе региональных и национальных языков, поддерживаемых для использования в конференциях с использованием телефонного номера Skype для бизнеса Server. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в организации.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импортирует каталоги конференций из Microsoft Office Communications Server 2007 R2 в Skype для бизнеса Server. Это помогает обеспечить взаимодействие между Skype для бизнеса Server и Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Создает новую коллекцию параметров сигналов двухтонального многочастотного набора (DTMF), используемых для телефонной связи.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров сигналов двухтонального многочастотного набора (DTMF), используемых для телефонной связи.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Изменяет параметры, которые определяют, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Изменяет параметры сигналов двухтонального многочастотного набора (DTMF), используемые для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Изменяет существующую абонентскую группу.  <br/> |
   
**Параметры политики ПИН-кодов**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках PIN-кодов, используемых в вашей организации. Проверка подлинности с помощью ПИН-кода позволяет пользователям получать доступ к Skype для бизнеса Server, предоставляя ПИН-код вместо имени пользователя и пароля.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Назначает клиентскую политику персональных идентификационных номеров (PIN-кодов) пользователю или группе пользователей.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Создает новую клиентскую политику персональных идентификационных номеров (PIN-кодов).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Удаляет указанную политику персонального идентификационного номера (PIN-кода).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Изменяет одну или несколько существующих политик использования клиентского персонального идентификационного номера (PIN-кода).  <br/> |
   

