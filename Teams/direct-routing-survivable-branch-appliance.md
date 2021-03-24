---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о решениях по маршрутиации голоса.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edf2c2a97bec2b167f1218d983d3c9f7fa4bd667
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096429"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Устройство ветвной ветви (SBA) для прямой маршрутинга


В редких случаях сайт клиента с прямой маршрутией для подключения к телефонной системе Майкрософт может привести к простою в Интернете.

Предположим, что сайт клиента ,называемый ветвью, временно не может подключиться к Облаку Майкрософт с помощью прямой маршрутинга. Однако интрасеть в филиале по-прежнему работает полностью, и пользователи могут подключиться к контроллеру границы сеанса (SBC), который обеспечивает подключение по ННР.

В этой статье описано, как использовать устройство SBA (Ветвь с возможностью сбоя), чтобы телефонная система Майкрософт и далее получала вызовы телефонной сети общего пользования (МСК) в случае сбоя.

## <a name="prerequisites"></a>Необходимые компоненты

Распространяемый код SBA предоставляется корпорацией Майкрософт поставщикам SBC, которые затем внедрят код в свои программы или распространят его отдельно, чтобы SBA запускался на отдельном VM- или аппаратном оборудовании. 

Чтобы получить последнюю версию встроенного ПО "Пограничный контроллер сеанса" с внедренным устройством Ветвной линии Скайп, обратитесь к поставщику SBC. Кроме того, требуется следующее:

- Чтобы клиент Microsoft Teams на сайте филиала мог использовать потоки мультимедиа непосредственно с SBC, необходимо настроить обход мультимедиа. 

- В SBA VM OS должен быть включен TLS1.2.

## <a name="supported-teams-clients"></a>Поддерживаемые клиенты Teams

Функция SBA поддерживается в следующих клиентах Microsoft Teams: 

- Microsoft Teams для рабочего стола Windows 

- Классические версии Microsoft Teams для macOS 

## <a name="how-it-works"></a>Принципы работы

Во время сбоя в Интернете клиент Teams должен автоматически переключиться на SBA, и постоянные звонки должны продолжаться без прерываний. От пользователя не требуется никаких действий. Как только клиент Teams обнаружит, что Интернет подключен, и все исходяющие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим службам Teams. SBA загрузит собранные записи о звонках в облако, и история зовов обновится, чтобы эти сведения были доступны для проверки администратором клиента. 

Если клиент Microsoft Teams работает в автономном режиме, доступны следующие функции, связанные со звонками: 

- Звонки через ДНР через местные службы SBA и SBC с мультимедиа, которые проходят через SBC.

- Получение звонков по ННР через местные службы SBA или SBC с мультимедиа, которые проходят через SBC. 

- Удержание и возобновление звонков по ННР.

## <a name="configuration"></a>Конфигурация

Чтобы функция SBA работала, клиент Teams должен знать, какие SBAs доступны на каждом сайте филиала и какие SBAs назначены пользователям этого сайта. Конфигурация может выполняться следующим образом:

1. Создайте SBAs.
2. Создайте политику ветвей ветвей Teams.
3. Назначьте политику пользователям.
4. Зарегистрируйте приложение для SBA в Azure Active Directory.

Вся настройка делается с помощью powerShell Skype для бизнеса Online. (Центр администрирования Teams пока не поддерживает функцию SBA direct Routing.) 

(Сведения о настройке SBC со ссылками на документацию поставщиков SBC см. в настройках граничного контроллера сеанса в конце этой статьи.)

### <a name="create-the-sbas"></a>Создание SBAs

Для создания SBAs используется New-CsTeamsSurvivableBranchAppliance. Этот cmdlet имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity  | Удостоверение SBA  |
| Fqdn | The FQDN of the SBA |
| Сайт | TenantNetworkSite, на котором находится SBA |
| Описание | Свободное форматирование текста |
|||

Например:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Создание политики ветвей ветвей Teams 

Для создания политики используется New-CsTeamsSurvivableBranchAppliancePolicy управления. Этот cmdlet имеет следующие параметры: Обратите внимание, что политика может содержать одно или несколько SBAs.

| Параметр| Описание |
| :------------|:-------|
| Identity | Удостоверение политики |
| BranchApplianceFqdns  | FQDN SBA на сайте |
||

Например:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Добавить или удалить SBAs из политики можно с помощью Set-CsTeamsSurvivableBranchAppliancePolicy-управления. Например: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Назначение политики пользователю

Чтобы назначить политику отдельным пользователям, используйте Grant-CsTeamsSurvivableBranchAppliancePolicy управления. Этот cmdlet имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity | Удостоверение пользователя |
| PolicyName | Удостоверение политики |
||

Например:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Вы можете удалить политику пользователя, $Null политику, как показано в следующем примере:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Регистрация приложения для SBA в Azure Active Directory

Чтобы другие SBA, используемые в клиенте, могли читать необходимые данные от Microsoft 365, необходимо зарегистрировать приложение для SBA в Azure Active Directory. 

Дополнительные сведения о регистрации приложений см. в следующих сведениях:

- [Разработка бизнес-приложений для Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Зарегистрируйте приложение на платформе удостоверений Майкрософт.](/azure/active-directory/develop/quickstart-register-app)  

Вам нужно зарегистрировать только одно приложение для использования всеми SBAs в клиенте. 

Для регистрации SBA требуются следующие значения: 

- ИД приложения (клиента) 
- Секрет клиента 

Для приложения SBA следует помнить следующее: 

- Имя может быть любым, что вы решаете.  
- Поддерживаемые типы учетных записей — только учетная запись в этом каталоге организации. 
- Uri web Redirect = ( Uri веб-перенаправления). https://login.microsoftonline.com/common/oauth2/nativeclient
- Неявный маркеры предоставления = маркеры доступа и токены ИД. 
- API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.
- Секрет клиента: вы можете использовать любое описание и срок действия. 
- Не забудьте скопировать секрет клиента сразу после его создания. 
- На вкладке "Обзор" отображается ИД приложения (клиента).

Затем выполните указанные далее действия.

1. Зарегистрируйте приложение.
2. Установите неявные маркеры предоставления.
3. За установите разрешения API.
4. Создайте секрет клиента.


## <a name="session-border-controller-configuration"></a>Настройка граничного геймпада сеанса 

Пошаговую инструкцию по настройке контроллера границы сеанса с помощью внедренного ветвного устройства см. в документации поставщика SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Лента](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Проблемы с отчетами

Сообщайте о проблемах в службе поддержки поставщика SBC. Сообщая о проблеме, указать, что у вас установлена ветвная устройство Скайп.

## <a name="known-issues"></a>Известные проблемы

- Применение новых устройств с ветвными устройствами с использованием ветвных устройств с подавными системами может занять некоторое время.

- Когда вы назначаете пользователю политику с возможностью ветвного устройства с возможностью сбоя, может потребоваться некоторое время, прежде чем SBA будет показан в выходе Get-CsOnlineUser. 

- Обратный просмотр номеров для контактов Azure AD не выполняется. 

- SBA не поддерживает параметры переадварки параметров. 

- Экстренные вызовы на номера, настроенные для динамических экстренных вызовов (E911), не поддерживаются.

- Результат Get-CsOnlineUser TeamsBranchSurvivabilityPolicy.