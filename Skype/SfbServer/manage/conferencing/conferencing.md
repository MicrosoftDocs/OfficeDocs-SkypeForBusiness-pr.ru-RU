---
title: Управление конференциями в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Сводка: сведения о том, как управлять Конференцией в Skype для бизнеса Server.'
ms.openlocfilehash: 55fd2ff645e6e95199b2558ef494eea019b155bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280427"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Управление конференциями в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как управлять Конференцией в Skype для бизнеса Server.
  
В этой статье описано, как управлять Конференцией. Дополнительные сведения о планировании и развертывании конференций можно найти [в разделе Планирование конференций в Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и [развертывание конференций в Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
В Skype для бизнеса Server вы управляете сведениями о конференциях, указывая параметры конфигурации и политики, как описано ниже. Обратите внимание на то, что термины Конференции и собрания иногда взаимозаменяемы. Но в целом вы можете представить собрание как конкретный экземпляр Конференции.
  
- **Настройки политики конференц-связи** охватывают широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников. Вы можете использовать политики конференц-связи для управления безопасностью, пропускной способностью и правовыми аспектами собраний.
    
    Обратите внимание на то, что политики конференц-связи применяются к пользователю или сайту и не применяются к конкретному собранию. Таким образом, приглашение на собрание для Конференции можно создать в течение нескольких недель, но перед началом Конференции ее следует применить к учетной записи Skype для бизнеса организатора собрания. 
    
    Если выделенная учетная запись используется для роли организатора собрания, политику конференц-связи можно оставить назначенной этой учетной записи. Если организатор собрания использует общую учетную запись Skype для бизнеса, она должна быть удалена после завершения Конференции.
    
- С помощью **параметров конфигурации собраний** задается тип собраний, которые могут создавать пользователи, а также определяется возможность и способ присоединения анонимных пользователей и пользователей с телефонным подключением к собраниям. Обратите внимание, что эти настройки действуют только для запланированных собраний. Конфигурации собраний применяются для каждого пула, сайта или глобально.
    
- **Параметры настройки конференц** -связи определяют максимально допустимый размер контента и выдач для собрания; Максимальная пропускная способность для службы конференц-связи с приложениями. ограничения хранилища и периоды срока действия; URL-адреса для внутренних и внешних загрузок поддерживаемого клиента; указатели на внутренние и внешние URL-адреса, в которых пользователи могут получить справку по Конференции и ресурсы; и порты, используемые для общего обмена приложениями, звука клиента, передачи файлов и мультимедийного трафика.
    
    These settings allow you to manage the actual servers themselves. Эти параметры можно настроить только с помощью командной консоли Skype для бизнеса Server. 
    
- **Параметры телефонного подключения** позволяют настроить данные и правила телефонного подключения. Для телефонного подключения можно задать такие данные, как номер для доступа, на вкладке "Конференц-связь" на панели управления, а также абонентскую группу, политику голосовой связи, маршрут и необходимость использования ТСОП, на вкладке "Маршрутизация голосовой связи" на панели управления.
    
- **Параметры политики ПИН-кода** позволяют задать ПИН-код, который будут использовать участники для телефонного подключения.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Управление конференциями с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server

Для управления большинством политик конференц-связи и параметров конфигурации можно использовать панель управления Skype для бизнеса Server или консоль управления Skype для бизнеса Server. Некоторые параметры конфигурации доступны только с помощью командной консоли Skype для бизнеса Server.
  
- Управление параметрами политики конференц-связи
    
  - На панели управления выберите **Конференц-связь | Политика конференц-связи**.
    
  - В PowerShell выполните поиск командлетов **-CsConferencingPolicy**.
    
- Управление параметрами конфигурации собраний
    
  - На панели управления выберите **Конференц-связь | Конфигурация собраний**.
    
  - В командной консоли управления Skype для бизнеса Server выполните поиск командлетов **-ксмитингконфигуратион** .
    
- Управление параметрами номера для телефонного подключения
    
  - На панели управления выберите **Конференц-связь | Номер для телефонного подключения**.
    
  - В командной консоли управления Skype для бизнеса Server выполните поиск командлетов **-ксдиалинконференЦинг** .
    
- Управление такими данными телефонного подключения, как абонентская группа, голосовая политика, маршрут и использование ТСОП 
    
  - На панели управления выберите **Конференц-связь | Маршрутизация голосовой связи**.
    
  - В командной консоли управления Skype для бизнеса Server выполните поиск командлетов **-ксдиалплан** и **-ксвоице** .
    
- Управление параметрами политики ПИН-кода
    
  - На панели управления выберите **Конференц-связь | Политика ПИН-кода**.
    
  - В командной консоли управления Skype для бизнеса Server выполните поиск командлетов **-кспинполици** .
    
- Для управления параметрами настройки конференц-связи необходимо использовать командную консоль управления Skype для бизнеса Server. Search for **-CsConferencingConfiguration** cmdlets.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Командлеты командной консоли Skype для бизнеса Server

Для управления конференцией вы можете использовать следующие командлеты командной консоли Skype для бизнеса Server: 
  
**Параметры политики конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, сконфигурированных для использования в вашей организации. Политики проведения конференций определяют функции и возможности, которые можно использовать в конференции, начиная с возможности использовать аудио и видеосвязь по протоколу IP и заканчивая максимальным количеством участников конференции.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет выбранную политику конференц-связи.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику определения конференц-связи.  <br/> |
   
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, в настоящее время используемых в организации. Параметры конфигурации собраний помогают задать тип собраний, который может создаваться пользователями, и управлять тем, как анонимные пользователи и пользователи, участвующие в конференц-связи с телефонным подключением, могут присоединяться к этим собраниям (или даже тем, могут ли они присоединяться).  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы. Обратите внимание, что эти параметры влияют только на запланированные собрания; они не влияют на нерегламентированные собрания, созданные с помощью команды "провести собрание" в Skype для бизнеса.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменяет параметры конфигурации собраний, используемые в настоящее время в организации.  <br/> |
   
**Параметры конфигурации конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации конференций для организации. Параметры конфигурации определяют максимальный допустимый размер содержимого и раздаточных материалов конференции, время хранения содержимого до его удаления и URL-адреса для внешней и внутренней загрузки поддерживаемого клиента.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференций.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Удаляет указанную коллекцию параметров конфигурации конференции.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Изменяет существующую коллекцию параметров конфигурации конференц-связи.  <br/> |
   
**Параметры конфигурации телефонного подключения**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Возвращает сведения о каталогах конференций, используемых в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Получение сведений о том, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Возвращает информацию обо всех номерах доступа к конференц-связи с телефонным подключением в организации.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Возвращает параметры сигналов двухтонального многочастотного набора (DTMF), используемых в конференциях. DTMF-набор позволяет пользователям, вошедшим в конференцию, управлять параметрами конференции (например, выключать или включать собственный звук, блокировать конференцию и т. п.) с помощью клавиш собственного телефона.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Возвращает список языков, в том числе языков и региональных стандартов, которые поддерживаются в конференц-связи с телефонным подключением в Skype для бизнеса Server. Эти языки используются для передачи звуковых сообщений и инструкций пользователям, участвующим в конференции по телефону.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Возвращает сведения о абонентских группах, используемых в вашей организации.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Назначает абонентскую группу одному или нескольким пользователям или группам.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Импорт каталогов конференций из Microsoft Office Communications Server 2007 R2 в Skype для бизнеса Server. Это помогает обеспечить взаимодействие между Skype для бизнеса Server и Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Перемещает существующий каталог конференции из одного пула в другой. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Создает каталог конференции для использования в организации. Каталоги конференций позволяют пользователям конференц-связи с телефонным подключением находить сведения о конференциях.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Создает номер доступа к конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Создает коллекцию параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее. В частности, возвращается информация о том, должны ли участники записать свое имя при присоединении к конференции и как система объявляет о том, что кто-то присоединился к конференции или вышел из нее.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров передачи сигналов двухтонального многочастотного набора (DTMF), используемых для конференц-связи с телефонным подключением.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Создает новую абонентскую группу.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Удаляет существующий каталог конференции. Каталоги конференций облегчают пользователям конференц-связи с телефонным подключением поиск сведений о конференциях.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Удаляет существующий номер доступа к конференции по коммутируемой линии.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Удаляет одну или несколько коллекций параметров конфигурации конференц-связи с телефонным подключением. Эти параметры определяют, как Skype для бизнеса Server отвечает на запросы пользователей к Конференции с телефонным подключением или выходом из нее.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию настроек двухтональной многочастотной (dual-tone multifrequency, DTMF) сигнализации, используемых для конференц-связи с телефонным подключением.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Изменяет значения свойств существующего номера доступа к конференц-связи с телефонным подключением. Конференц-связь с телефонным подключением позволяет присоединяться к звуковому каналу конференции с помощью обычного телефона, мобильного телефона или другого устройства в телефонной сети общего пользования (ТСОП).  <br/> |
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
   
**Другие параметры конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Отключение в конференц-зале Skype для бизнеса Server. Комната переговоров — это устройство для проведения конференций, предназначенное для обработки сценариев видеоконференций и совместной работы в небольших конференц-залах. При отключении объекта комнаты для собрания удаляются все атрибуты Active Directory, связанные с сервером Skype для бизнеса, которые назначены учетной записи пользователя, представляющей комнату собраний. Однако сама учетная запись Active Directory не удаляется.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Включает Конференц-зал Skype для бизнеса Server. Чтобы включить комнату для собраний, нужно сначала создать в Active Directory учетную запись пользователя, представляющую систему. Следует отметить, что хотя объекты комнат для собраний основываются на учетных записях пользователей, они не будут видны при запуске командлета Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Возвращает сведения о заявлении об отказе от прав конференции, которое используется в вашей организации. Заявление об отказе от прав — это сообщение, которое отображается пользователям, присоединяющимся к конференции посредством гиперссылки (например, пользователи могут открыть ссылку на конференцию в браузере, например Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Возвращает сведения обо всех комнатах собраний Skype для бизнеса Server, настроенных для использования в Организации.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Перемещение объекта комнаты собраний Skype для бизнеса Server из одного пула регистраторов в другой.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Удаляет текст из заголовка и сообщения заявления от отказе от прав для конференции, которое используется в вашей организации. Заявление об отказе от прав конференции — это сообщение, отображаемое для пользователей, которые присоединяются к конференции с помощью гиперссылки (например, пользователи, которые открывают ссылку на конференцию в браузере, например, Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Изменение значений свойств существующей комнаты для собраний Skype для бизнеса Server.  <br/> |
   
**Параметры тестирования**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Проверяет способность пары пользователей принимать участие в конференции с общим доступом к приложениям.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Проверяет, может ли пользователь подключиться к своему поставщику услуг аудиоконференций. Поставщик услуг аудиоконференций — это сторонняя компания, предоставляющая организациям услуги по проведению аудиоконференций. Помимо всего прочего поставщики услуг аудиоконференций позволяют пользователям, расположенным за пределами организации и не подключенным к корпоративной сети или Интернету, участвовать в конференции или собрании с помощью аудиосвязи.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Проверяет возможность включения двух пользователей в аудио- или видеоконференцию.  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Проверка того, могут ли пользователи присоединиться к веб-конференции Skype для бизнеса Server, которая включает в себя такие действия, как предоставление общего просмотра или Просмотр слайдов PowerPoint, досок и опросов. Командлет также проверяет, может ли служба веб-конференций Skype для бизнеса Server найти сервер Office Web Apps, и что клиент может загрузить файл PowerPoint для широковещательного показа с помощью Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Выполняет проверку, может ли пользователь принять участие в сеансе конференц-связи с телефонным подключением.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Тестирует номер телефона на абонентскую группу (которая раньше называлась профилем местоположения) и возвращает правило нормализации, которое будет применяться к номеру, а также преобразованный номер после применения правила нормализации.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Проверка способности трех пользователей принять участие в конференции службы Mobility Service в Skype для бизнеса Server. Служба Mobility Service позволяет пользователям мобильных телефонов, таких как iPhone и телефоны Windows, выполнять такие действия, как обмен мгновенными сообщениями и сведения о присутствии; Храните и изменяйте голосовую почту внутренне, а не с поставщиком услуг беспроводной связи; и воспользуйтесь преимуществами возможностей Skype для бизнеса Server, таких как звонки через Конференц-связь с телефонным подключением.  <br/> **Примечание.** Клиенты, использующие МККС, не поддерживаются в Skype для бизнеса Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Проверяет возможность пары пользователей планировать сетевую конференцию, присоединяться к ней, а затем проводить ее с помощью веб-интерфейса API объединенных коммуникаций (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Возвращает диагностические сведения о возможностях конференц-связи с данными, включенных в Skype для бизнеса Server.  <br/> |
   

