---
title: Управление conferencing в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: Сводка. Узнайте, как управлять конференцией в Skype для бизнеса Server.
ms.openlocfilehash: 122b7d797983df9bb3ef6252234099869650a66e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845462"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Управление conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять конференцией в Skype для бизнеса Server.
  
В этом разделе описывается, как управлять конференцией. Дополнительные сведения о планировании и развертывании конференций см. в Skype для бизнеса Server Plan [for conferencing in Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
В Skype для бизнеса Server вы управляете сведениями о конференциации, указав параметры конфигурации и политики следующим образом. Обратите внимание, что термины conferencing и meeting иногда используются взаимозаменяемо. Но, как правило, собрание можно придумать как конкретный экземпляр проведения собраний.
  
- **Параметры политики** конференциации охватывают широкий спектр параметров планирования и участия, начиная от того, может ли собрание включать аудио- и видео IP-адресов до максимального числа людей, которые могут присутствовать. Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.
    
    Обратите внимание, что политики проведения собраний применяются к пользователю или сайту и не могут применяться к определенному собранию. Поэтому приглашение на собрание может быть создано за несколько недель до начала конференции, но политика ограничительных конференций должна применяться к учетной записи организатора собрания Skype для бизнеса перед началом конференции. 
    
    Если выделенная учетная запись используется для роли организатора собраний, политика конференций может оставаться назначенной этой учетной записи. Если организатор собрания использует общую Skype для бизнеса учетную запись, политика должна быть удалена после завершения конференции.
    
- **Параметры** конфигурации собраний диктуют тип собраний, которые пользователи могут создавать, в дополнение к контролю того, как (или даже если) анонимные пользователи и пользователи телефонных собраний могут присоединяться к этим собраниям. Обратите внимание, что эти параметры влияют только на запланированные собрания. Конфигурации собраний применяются в пуле, на сайте или в глобальном масштабе.
    
- **Параметры конфигурации конференций** определяют такие вещи, как максимально допустимый размер для контента собраний и раздаток; максимальный объем пропускной способности для службы конференций общего доступа к приложениям; ограничения хранения и сроки действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получать помощь и ресурсы для конференциалов; и порты, используемые для общего доступа к приложениям, клиентского аудиозаписи, передачи файлов и трафика мультимедиа.
    
    Эти параметры позволяют управлять самими серверами. Эти параметры можно установить только с помощью Skype для бизнеса Server управленческой оболочки. 
    
- **Параметры доступа с диалогом** позволяют определить, в ли и как пользователи звонит с телефона. Некоторые сведения о доступе к диалоговому номеру, например номер доступа, указаны на вкладке "Конференция панели управления" и некоторые сведения о диалоговом номере , такие как телефонная группа, голосовая политика, маршрут и использование PSTN, на вкладке Голосовая маршрутия панели управления.
    
- **Параметры политики ПИН-кода** позволяют назвать и определить ПИН-код, который участники используют для доступа к диалоговому входу.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Управление конференцией с помощью панели Skype для бизнеса Server или с помощью Skype для бизнеса Server управленческой оболочки

Вы можете управлять большинством политик и параметров конфигурации с помощью Skype для бизнеса Server панели управления или с помощью Skype для бизнеса Server Management Shell. Некоторые параметры конфигурации доступны только с помощью Skype для бизнеса Server управленческой оболочки.
  
- Управление настройками политики конференций:
    
  - В панели управления выберите **| Политика conferencing**.
    
  - В PowerShell найди **кодлеты -CsConferencingPolicy.**
    
- Управление настройками конфигурации собраний:
    
  - В панели управления выберите **| Конфигурация собраний.**
    
  - В Skype для бизнеса Server управленческой оболочки ищите команды **-CsMeetingConfiguration.**
    
- Для управления настройками номеров доступа к диалоговому номеру:
    
  - В панели управления выберите **| Номер доступа с диалогом.**
    
  - В Skype для бизнеса Server управленческой оболочки ищите **команды CsDialInConferencing.**
    
- Управление данными о доступе к диалоговым номерам, такими как телефонная политика, голосовая политика, маршрут и использование PSTN: 
    
  - В панели управления выберите **| Маршрутивка голосовой почты**.
    
  - В Skype для бизнеса Server управленческой оболочки ищите команды **-CsDialPlan** и **CsVoice.**
    
- Управление настройками политики ПИН-кода:
    
  - В панели управления выберите **| Политика PIN-кода.**
    
  - В Skype для бизнеса Server управленческой оболочки ищите команды **-CsPinPolicy.**
    
- Для управления настройками конфигурации конференций необходимо использовать Skype для бизнеса Server management Shell. Поиск **смещающихся CsConferencingConfiguration.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype для бизнеса Server Команды управленческой оболочки

Для управления conferencing можно использовать Skype для бизнеса Server команды Management Shell: 
  
**Параметры политики conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации. Политики проведения конференций определяют функции и возможности, которые можно использовать в конференции, начиная с возможности использовать аудио и видеосвязь по протоколу IP и заканчивая максимальным количеством участников конференции.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет указанную политику конференций.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику конференции.  <br/> |
   
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, которые в настоящее время используются в организации. Параметры конфигурации собраний помогают определять тип собраний, которые пользователи могут создавать, и контролировать, как (или даже если) анонимные пользователи и пользователи телефонных собраний могут присоединяться к этим собраниям.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы. Обратите внимание, что эти параметры влияют только на запланированные собрания; они не влияют на собрания, созданные путем нажатия параметра Meet Now в Skype для бизнеса.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменяет параметры конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
   
**Параметры конфигурации конференциации**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференций для организации. Параметры конфигурации определяют максимальный допустимый размер содержимого и раздаточных материалов конференции, время хранения содержимого до его удаления и URL-адреса для внешней и внутренней загрузки поддерживаемого клиента.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференций.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации конференции.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
**Параметры конфигурации dial-in**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Извлекает сведения о том, как Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры многочастотной сигнализации с двойным тоном (DTMF), используемые для телефонных конференциалов. Двухтональный многочастотный набор позволяет пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включать и отключать собственный микрофон или блокировать и разблокировать конференцию) с помощью клавиатуры телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе региональных и национальных языков, поддерживаемых для Skype для бизнеса Server конференц-связи. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в организации.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импортирует каталоги конференций Microsoft Office Communications Server 2007 R2 в Skype для бизнеса Server. Это позволяет обеспечить взаимодействие между Skype для бизнеса Server и Office communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров передачи сигналов двухтонального многочастотного набора (DTMF), используемых для конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции. Каталоги конференций облегчают пользователям конференц-связи с телефонным подключением поиск сведений о конференциях.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют Skype для бизнеса Server, когда пользователи присоединяются к конференции или покидают ее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию двухтонных многочастотных параметров сигнализации, используемых для телефонных собраний.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением. Конференц-связь с телефонным подключением позволяет присоединяться к звуковому каналу конференции с помощью обычного телефона, мобильного телефона или другого устройства в телефонной сети общего пользования (PSTN).  <br/> |
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
   
**Другие параметры конференций**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Отключает Skype для бизнеса Server комнату собраний. Комната для собраний — это средство конференц-связи, предназначенное для обеспечения видеосвязи и совместной работы при проведении конференций в небольших конференц-залах. При отключке объекта комнаты собраний удаляются Skype для бизнеса Server атрибуты Active Directory, присвоенные учетной записи пользователя, которая представляет зал собраний. Однако сама учетная запись пользователя Active Directory не удаляется.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Включает комнату Skype для бизнеса Server собраний. Чтобы включить комнату для собраний, нужно сначала создать в Active Directory учетную запись пользователя, представляющую систему. Следует отметить, что хотя объекты комнат для собраний основываются на учетных записях пользователей, они не будут видны при запуске командлета Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Возвращает сведения о заявлении об отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав — это сообщение, которое отображается пользователям, присоединяющимся к конференции посредством гиперссылки (например, пользователи могут открыть ссылку на конференцию в браузере, таком как Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Возвращает сведения обо всех Skype для бизнеса Server залах собраний, настроенных для использования в организации.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Перемещает объект Skype для бизнеса Server из одного пула регистратора в другой.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Удаляет текст из заголовка и сообщения заявления от отказе от прав конференции, используемом в вашей организации. Заявление об отказе от прав конференции — это сообщение, отображаемое для пользователей, которые присоединяются к конференции с помощью гиперссылки (например, пользователи, которые открывают ссылку на конференцию в браузере, таком как Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Изменяет значения свойств существующего Skype для бизнеса Server комнаты собраний.  <br/> |
   
**Параметры тестирования**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Проверяет способность пары пользователей принимать участие в конференции с общим доступом к приложениям.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Проверяет, может ли пользователь подключиться к своему поставщику услуг аудиоконференций. Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций. Помимо всего прочего поставщики услуг аудиоконференций позволяют пользователям, расположенным за пределами организации и не подключенным к корпоративной сети или Интернету, участвовать в конференции или собрании с помощью аудиосвязи.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Проверяет возможность включения двух пользователей в аудио- или видеоконференцию.  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Проверяет, может ли пара пользователей участвовать в веб-конференции Skype для бизнеса Server, которая включает такие действия, как совместное использование или просмотр PowerPoint слайдов, доски или опросы. Кроме того, в этом проекте проверяется, что Skype для бизнеса Server веб-Office может обнаружить Office веб-сервер приложений и что клиент может загрузить файл PowerPoint для Office веб-приложения Server.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Проверяет, может ли пользователь принять участие в сеансе телефонной встречи.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Тестирует номер телефона на абонентскую группу (которая раньше называлась профилем местоположения) и возвращает правило нормализации, которое будет применяться к номеру, а также преобразованный номер после применения правила нормализации.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Проверяет возможность участия трех пользователей в конференции Skype для бизнеса Server мобильности. Служба мобильности позволяет пользователям мобильных телефонов, таких как iPhone и Windows, делать такие вещи, как обмен мгновенными сообщениями и сведения о присутствии; хранение и извлечение голосовой почты внутренне, а не с их беспроводным поставщиком; и воспользоваться преимуществами Skype для бизнеса Server, таких как call via Work и dial-out conferencing.  <br/> **Примечание:** Клиенты, которые используют MCX, не поддерживаются Skype для бизнеса Server 2019 г.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Проверяет способность пары пользователей планировать, присоединяться и проводить онлайн-конференцию с помощью API Единой системы связи (UCWA).  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Возвращает диагностические сведения для возможностей конференциинга данных, включенных в Skype для бизнеса Server.  <br/> |
