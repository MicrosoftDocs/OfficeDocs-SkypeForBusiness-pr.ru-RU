---
title: Управление Конференцией с телефонным подключением в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Сводка: сведения об управлении Конференц-связь с телефонным подключением в Skype для бизнеса Server.'
ms.openlocfilehash: e27ee84769d2ba25b3d3ea6689c7125889b4f80e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283777"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Управление Конференцией с телефонным подключением в Skype для бизнеса Server
 
**Сводка:** Сведения об управлении Конференц-связь с телефонным подключением в Skype для бизнеса Server.
  
В этом разделе описывается, как управлять конференц-связью с телефонным подключением. Дополнительные сведения о планировании и настройке конференц-связи с телефонным подключением при развертывании можно найти в разделе [планирование конференц-связи с телефонным подключением в Skype для бизнеса Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) и [настройке конференц-связи с телефонным подключением в Skype для бизнеса Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Вы можете выполнять следующие задачи для управления Конференцией с телефонным подключением, а также включать и отключать Конференц-связь с телефонным подключением, управлять номерами доступа, управлять политиками закрепления для конференций с телефонным подключением, управлять присоединением к Конференции и оставлять объявления, изменять сопоставления клавиш для DTMF. команды и пользователи с приглашениями на Конференц-связь с телефонным подключением. 
  
Дополнительные сведения об управлении абонентными тарифами можно найти [в разделе Создание и изменение абонентской группы в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Дополнительные сведения об использовании PSTN можно найти [в разделе Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Skype для бизнеса](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Настройка конференц-связи с телефонным подключением с помощью панели управления Skype для бизнеса Server

Чтобы управлять информацией о конференц-связи с телефонным подключением, выполните указанные ниже действия.
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. На левой панели навигации щелкните элемент **Конференция**.
    
Чтобы управлять информацией об абонентских группах и использовании ТСОП, выполните указанные ниже действия.
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Управление Конференцией с телефонным подключением с помощью командной консоли Skype для бизнеса Server

Чтобы настроить Конференц-связь с телефонным подключением с помощью командной консоли Skype для бизнеса Server, выполните следующие командлеты:
  
**Параметры конференц-связи с телефонным подключением**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Получение сведений о том, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры сигналов двухтонального многочастотного набора (DTMF), используемых в конференциях. DTMF-набор позволяет пользователям, вошедшим в конференцию, управлять параметрами конференции (например, выключать или включать собственный звук, блокировать конференцию и т. п.) с помощью клавиш собственного телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе языков и региональных стандартов, которые поддерживаются в конференц-связи с телефонным подключением в Skype для бизнеса Server. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в вашей организации.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импорт каталогов конференций из Microsoft Office Communications Server 2007 R2 в Skype для бизнеса Server. Это помогает обеспечить взаимодействие между Skype для бизнеса Server и Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Создает новую коллекцию параметров передачи сигналов двухтонального многочастотного набора (DTMF), используемых для конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию настроек двухтональной многочастотной (dual-tone multifrequency, DTMF) сигнализации, используемых для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Изменение параметров, которые определяют, как отвечает Skype для бизнеса Server при присоединении к Конференции с телефонным подключением или выходе из нее.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Изменяет параметры сигналов двухтонального многочастотного набора (DTMF), используемые для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Изменяет существующую абонентскую группу.  <br/> |
   
**Параметры политики ПИН-кода**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках ПИН-кодов, используемых в вашей организации. Проверка подлинности с помощью ПИН-кода позволяет пользователям получить доступ к серверу Skype для бизнеса, указав PIN-код вместо имени пользователя и пароля.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Назначает клиентскую политику персональных идентификационных номеров (ПИН-кодов) пользователю или группе пользователей.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Создает новую клиентскую политику персональных идентификационных номеров (ПИН-кодов).  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Удаляет указанную политику персонального идентификационного номера (ПИН-кода).  <br/> |
|[Set-Кспинполици](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Изменяет одну или несколько существующих политик использования клиентского персонального идентификационного номера (ПИН-кода).  <br/> |
   

