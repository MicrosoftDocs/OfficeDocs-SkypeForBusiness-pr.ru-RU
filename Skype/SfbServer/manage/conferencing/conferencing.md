---
title: Управление conferencing в Skype для бизнеса Server
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
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: Сводка. Узнайте, как управлять conferencing в Skype для бизнеса Server.
ms.openlocfilehash: b1df4a339d7764c86ba76804dc67d1e1f11fc397
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810219"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Управление conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять conferencing в Skype для бизнеса Server.
  
В этом разделе описывается, как управлять conferencing. Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
В Skype для бизнеса Server вы управляете сведениями о конфигурации и параметрах политики следующим образом. Обратите внимание, что термины "conferencing" и "meeting" иногда взаимозаменяемы. Но, как правило, собрание можно использовать в качестве конкретного экземпляра для проведения собраний.
  
- **Параметры политики** аудиоконференций охватывают широкий спектр параметров планирования и участия, от того, может ли собрание включать IP-аудио и видео, до максимального количества участников. Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.
    
    Обратите внимание, что политики проведения собраний применяются к пользователю или сайту и не могут применяться к конкретному собранию. Таким образом, приглашение на собрание для конференции можно создать за несколько недель до начала конференции, но ограничительную политику конференц-связи следует применить к учетной записи организатора собрания в Skype для бизнеса перед началом конференции. 
    
    Если для роли организатора собрания используется выделенная учетная запись, политика конференций может оставаться назначенной этой учетной записи. Если организатор собрания использует общую учетную запись Skype для бизнеса, политику необходимо удалить после завершения конференции.
    
- **Параметры** конфигурации собраний определяют тип собраний, которые могут создавать пользователи, в дополнение к управлению тем, как анонимные пользователи и пользователи с телефонным доступом могут присоединяться к этим собраниям (или даже могут ли они присоединяться). Обратите внимание, что эти параметры влияют только на запланированные собрания. Конфигурации собраний применяются к пулу, сайту или глобально.
    
- **Параметры конфигурации проведения** собраний определяют такие параметры, как максимальный допустимый размер содержимого собрания и раздаточной информации; максимальный объем пропускной способности для службы общего доступа к приложениям; ограничения хранилища и сроки действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получить справку и ресурсы по видеоконференциям; порты, используемые для общего доступа к приложениям, клиентского звука, передачи файлов и трафика мультимедиа;
    
    Эти параметры позволяют управлять фактическими серверами самостоятельно. Эти параметры можно настроить только с помощью оболочки управления Skype для бизнеса Server. 
    
- **Параметры доступа с** телефонным доступом позволяют определить, будут ли пользователи звонить с телефона и как это делать. Некоторые сведения о доступе к телефонной сети, такие как номер доступа, указываются на вкладке "Панель управления" и некоторые сведения о телефонном под управлением ( например, о телефонной группе, политике голосовой почты, маршруте и использовании PSTN) на вкладке "Маршрут голосовой почты" панели управления.
    
- **Параметры политики ПИН-кодов** позволяют назвать и определить ПИН-код, который участники используют для телефонного доступа.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Manage conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell

Большинство политик и параметров конфигурации можно управлять с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell. Некоторые параметры конфигурации доступны только с помощью skype для бизнеса Server Management Shell.
  
- Для управления настройками политики conferencing:
    
  - На панели управления выберите **| Политика conferencing**.
    
  - В PowerShell найди по запросу **-CsConferencingPolicy.**
    
- Для управления настройками конфигурации собраний:
    
  - На панели управления выберите **| Конфигурация собрания.**
    
  - In Skype for Business Server Management Shell, search for the **-CsMeetingConfiguration** cmdlets.
    
- Для управления настройками номеров доступа к телефонной сети:
    
  - На панели управления выберите **| Номер доступа для телефонного доступа.**
    
  - In Skype for Business Server Management Shell, search for the **-CsDialInConferencing** cmdlets.
    
- Для управления сведениями о доступе к телефонной сети, такими как номера, политика голосовой почты, маршрут и использование PSTN: 
    
  - На панели управления выберите **| Маршрутная маршрутка голосовой почты.**
    
  - In Skype for Business Server Management Shell, search for the **-CsDialPlan** and **-CsVoice** cmdlets.
    
- Для управления настройками политики ПИН-кодов:
    
  - На панели управления выберите **| Политика ПИН-кодов.**
    
  - In Skype for Business Server Management Shell, search for the **-CsPinPolicy** cmdlets.
    
- Для управления настройками конфигурации необходимо использовать skype for Business Server Management Shell. Поиск по **запросу -CsConferencingConfiguration.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Management Shell cmdlets

Для управления доступом к конференциям можно использовать следующие cmdlets skype for Business Server Management Shell: 
  
**Параметры политики conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации. Политики проведения конференций определяют функции и возможности, которые можно использовать в конференции, начиная с возможности использовать аудио и видеосвязь по протоколу IP и заканчивая максимальным количеством участников конференции.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет указанную политику.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику conferencing.  <br/> |
   
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, которые в настоящее время используются в организации. Параметры конфигурации собраний помогают определять тип собраний, которые могут создавать пользователи, а также управлять тем, как анонимные пользователи и пользователи с комконференцией могут присоединяться к этим собраниям (или даже могут ли они) присоединяться к ним.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы. Обратите внимание, что эти параметры влияют только на запланированные собрания; Они не влияют на нечеткие собрания, созданные с помощью параметра "Выполнить собрание" в Skype для бизнеса.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменяет параметры конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
   
**Параметры конфигурации conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференций для организации. Параметры конфигурации определяют максимальный допустимый размер содержимого и раздаточных материалов конференции, время хранения содержимого до его удаления и URL-адреса для внешней и внутренней загрузки поддерживаемого клиента.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференций.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации конференции.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
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
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров передачи сигналов двухтонального многочастотного набора (DTMF), используемых для конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции. Каталоги конференций облегчают пользователям конференц-связи с телефонным подключением поиск сведений о конференциях.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server реагирует, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров сигналов двухтонального многочастотного набора (DTMF), используемых для телефонной связи.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением. Конференц-связь с телефонным подключением позволяет присоединяться к звуковому каналу конференции с помощью обычного телефона, мобильного телефона или другого устройства в телефонной сети общего пользования (PSTN).  <br/> |
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
   
**Другие параметры conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Отключает комнату для собраний Skype для бизнеса Server. Комната для собраний — это средство конференц-связи, предназначенное для обеспечения видеосвязи и совместной работы при проведении конференций в небольших конференц-залах. При отключке объекта комнаты для собраний удаляются все атрибуты Active Directory, определенные в Skype для бизнеса Server, которые назначены учетной записи пользователя, которая представляет комнату для собраний. Однако сама учетная запись пользователя Active Directory не удаляется.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Включает комнату для собраний Skype для бизнеса Server. Чтобы включить комнату для собраний, нужно сначала создать в Active Directory учетную запись пользователя, представляющую систему. Следует отметить, что хотя объекты комнат для собраний основываются на учетных записях пользователей, они не будут видны при запуске командлета Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Возвращает сведения о заявлении об отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав — это сообщение, которое отображается пользователям, присоединяющимся к конференции посредством гиперссылки (например, пользователи могут открыть ссылку на конференцию в браузере, таком как Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Возвращает сведения обо всех комнатах для собраний Skype для бизнеса Server, настроенных для использования в организации.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Перемещает объект комнаты для собраний Skype для бизнеса Server из одного пула регистратора в другой.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Удаляет текст из заголовка и сообщения заявления от отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав конференции — это сообщение, отображаемое для пользователей, которые присоединяются к конференции с помощью гиперссылки (например, пользователи, которые открывают ссылку на конференцию в браузере, таком как Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Изменяет значения свойств существующей комнаты для собраний Skype для бизнеса Server.  <br/> |
   
**Параметры тестирования**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Проверяет способность пары пользователей принимать участие в конференции с общим доступом к приложениям.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Проверяет, может ли пользователь подключиться к своему поставщику услуг аудиоконференций. Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций. Помимо всего прочего поставщики услуг аудиоконференций позволяют пользователям, расположенным за пределами организации и не подключенным к корпоративной сети или Интернету, участвовать в конференции или собрании с помощью аудиосвязи.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Проверяет возможность включения двух пользователей в аудио- или видеоконференцию.  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Проверяет, может ли пара пользователей участвовать в веб-конференции Skype для бизнеса Server, которая включает такие действия, как общий доступ или просмотр слайдов PowerPoint, доской или опросов. Кроме того, он проверяет, может ли служба веб-конференций Skype для бизнеса Server обнаружить сервер Office Web Apps и что клиент может отправить файл PowerPoint для вещания сервером Office Web Apps.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Проверяет, может ли пользователь принимать участие в сеансе телефонной сети.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Тестирует номер телефона на абонентскую группу (которая раньше называлась профилем местоположения) и возвращает правило нормализации, которое будет применяться к номеру, а также преобразованный номер после применения правила нормализации.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Проверяет возможность участия трех пользователей в конференции Skype для бизнеса Server Mobility Service. Служба Mobility Service позволяет пользователям мобильных телефонов, таких как iPhone и Windows Phones, обмениваться мгновенными сообщениями и сведениями о присутствии; хранение и извлечение голосовой почты внутри организации, а не у поставщика услуг беспроводной связи; и воспользоваться такими возможностями Skype для бизнеса Server, как "Позвонить с работы" и "С помощью телефонного звонка".  <br/> **Примечание.** Клиенты, которые используют MCX, не поддерживаются в Skype для бизнеса Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Проверяет возможность пары пользователей планировать, присоединяться к конференции, а затем проводить онлайн-конференцию с помощью веб-API объединенных коммуникаций (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Возвращает диагностические сведения о возможностях передачи данных, включенных в Skype для бизнеса Server.  <br/> |
   

