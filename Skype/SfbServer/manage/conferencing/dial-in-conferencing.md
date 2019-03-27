---
title: Управление конференц-связи в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Сводка: Узнайте, как управлять конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 109f40e66feda81098f09689a862ce219ac2f676
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884938"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Управление конференц-связи в Скайп для Business Server
 
**Сводка:** Сведения об управлении конференц-связи в Скайп для Business Server.
  
В этом разделе описывается, как управлять конференц-связью с телефонным подключением. Дополнительные сведения о планировании и настройке конференц-связи во время развертывания [план для конференций в Скайп для Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) и [Настройка телефонных конференций в Скайп для Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md)см.
  
Можно выполнить следующие задачи для управления конференц-связи: включить или отключить телефонных конференций, управление номеров доступа, управление политиками ПИН-код для связи с телефонным подключением, управление присоединиться к конференции и оставьте извещения, изменение сопоставления клавиш для DTMF команды и приветствие пользователей для конференц-связи. 
  
Дополнительные сведения об управлении абонентских групп можно [Создание и изменение абонентской группы в Скайп для Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Дополнительные сведения об использовании ТСОП можно [Настройка политик голосовой связи, записей использования ТСОП и маршрутов голосовых вызовов в Скайп для бизнеса](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Управление конференц-связи с помощью Скайп для панели управления Business Server

Чтобы управлять информацией о конференц-связи с телефонным подключением, выполните указанные ниже действия.
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. На левой панели навигации щелкните элемент **Конференция**.
    
Чтобы управлять информацией об абонентских группах и использовании ТСОП, выполните указанные ниже действия.
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Управление конференц-связи с помощью Скайп для консоли Business Server

Управление конференц-связи с помощью Скайп для консоли Business Server, используйте следующие командлеты:
  
**Параметры конференц-связи с телефонным подключением**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Извлекает сведения о как Скайп для Business Server реагирует пользователей присоединиться к или покинуть конференц-связи.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры сигналов двухтонального многочастотного набора (DTMF), используемых в конференциях. DTMF-набор позволяет пользователям, вошедшим в конференцию, управлять параметрами конференции (например, выключать или включать собственный звук, блокировать конференцию и т. п.) с помощью клавиш собственного телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе язык/меньшей языки, поддерживаемые для использования с Скайп для Business Server телефонных конференций. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в вашей организации.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импортирует каталоги конференций из Microsoft Office Communications Server 2007 R2 Скайп для Business Server. Это позволяет обеспечить взаимодействие между Скайп для Business Server и Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Скайп для Business Server реагирует пользователей присоединиться к или покинуть конференц-связи. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Создает новую коллекцию параметров передачи сигналов двухтонального многочастотного набора (DTMF), используемых для конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Скайп для Business Server реагирует пользователей присоединиться к или покинуть конференц-связи.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию настроек двухтональной многочастотной (dual-tone multifrequency, DTMF) сигнализации, используемых для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Изменяет параметры, определяющие, как Скайп для Business Server реагирует пользователей присоединиться к или покинуть конференц-связи.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Изменяет параметры сигналов двухтонального многочастотного набора (DTMF), используемые для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Изменяет существующую абонентскую группу.  <br/> |
   
**Параметры политики ПИН-кода**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках ПИН-кодов, используемых в вашей организации. Проверка подлинности ПИН-КОДОВ позволяет пользователям обращаться к Скайп для Business Server с указанием ПИН-код вместо имени пользователя и пароля.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Назначает клиентскую политику персональных идентификационных номеров (ПИН-кодов) пользователю или группе пользователей.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Создает новую клиентскую политику персональных идентификационных номеров (ПИН-кодов).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Удаляет указанную политику персонального идентификационного номера (ПИН-кода).  <br/> |
|[SET-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Изменяет одну или несколько существующих политик использования клиентского персонального идентификационного номера (ПИН-кода).  <br/> |
   

