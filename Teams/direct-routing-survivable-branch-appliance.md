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
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о перенаправке голосовой связи.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589243"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Ветвное устройство (SBA) для прямой маршрутии


Иногда на сайте клиента с использованием прямой маршрутии для подключения к Телефон (Майкрософт) система может возникнуть скайп в Интернете.

Предположим, что сайт клиента , называемый ветвью, временно не может подключиться к Microsoft Cloud с помощью прямой маршрутии. Однако интрасеть внутри ветви по-прежнему работает полностью, и пользователи могут подключиться к контроллеру границы сеанса (SBC), который обеспечивает подключение по STN.

В этой статье описано, как с помощью устройства SBA (СР) можно продолжать звонить и принимать звонки по телефонной сети общего пользования (PSTN) в случае сбоя в системе Телефон (Майкрософт).

## <a name="prerequisites"></a>Необходимые компоненты

Код SBA предоставляется корпорацией Майкрософт поставщикам SBC, которые затем внедрили код в свое программное обеспечение или распространяли его отдельно для запуска SBA на отдельном VM-устройстве или оборудовании. 

Чтобы получить последнюю версию встроенного постройного постройки "Контроллер границы сеанса" с внедренным устройством ветвной ветви "Ветвь", обратитесь к поставщику SBC. Кроме того, требуется следующее:

- Чтобы клиент Microsoft Teams на сайте филиала мог иметь поток мультимедиа непосредственно с SBC, необходимо настроить обход мультимедиа. 

- В SBA VM OS должна быть включена TLS1.2.

## <a name="supported-teams-clients"></a>Поддерживаемые Teams клиентов

Функция SBA поддерживается в следующих клиентах Microsoft Teams: 

- Microsoft Teams Windows рабочего стола 

- Microsoft Teams macOS 

## <a name="how-it-works"></a>Принципы работы

Во время сбоя в Интернете клиент должен Teams автоматически переключиться на SBA, а постоянные звонки должны продолжаться без прерываний. Пользователю не требуется никаких действий. Как только клиент Teams обнаружит подключение к Интернету и все исходяющие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим Teams службам. SBA загрузит собранные записи данных об звонках в облако, и история зовов будет обновлена, чтобы эта информация была доступна для проверки администратором клиента. 

Если клиент Microsoft Teams в автономном режиме, доступны следующие функции, связанные со звонками: 

- Звонки через ДНР через локальный SBA или SBC с потоком мультимедиа через SBC.

- Прием звонков по ДНР через локальный SBA или SBC с потоком мультимедиа через SBC. 

- Удержание и возобновление звонков по ОКП.

## <a name="configuration"></a>Конфигурация

Чтобы функция SBA работала, Teams должен знать, какие SBAs доступны на каждом сайте филиала и какие они назначены пользователям на этом сайте. Для настройки выполните следующие действия:

1. Создайте SBAs.
2. Создайте политику Teams ветвей ветвей.
3. Назначьте политику пользователям.
4. Зарегистрируйте приложение для SBA в Azure Active Directory.

Вся настройка делается с Skype для бизнеса PowerShell. (Центр администрирования Teams пока не поддерживает функцию SBA прямой маршрутии.) 

(Сведения о настройке SBC со ссылками на документацию поставщиков SBC см. в статье Настройка контроллера границы сеанса в конце этой статьи.)

### <a name="create-the-sbas"></a>Создание SBAs

Для создания SBAs используется New-CsTeamsSurvivableBranchAppliance SBAs. Этот cmdlet имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity  | Удостоверение SBA  |
| Fqdn | The FQDN of the SBA |
| Сайт | TenantNetworkSite, на котором находится SBA |
| Описание | Свободный формат текста |
|||

Например:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Создание политики Teams ветвей 

Для создания политики используется New-CsTeamsSurvivableBranchAppliancePolicy. Этот cmdlet имеет следующие параметры: Обратите внимание, что политика может содержать один или несколько SBAs.

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

Вы можете добавить или удалить SBAs из политики с помощью Set-CsTeamsSurvivableBranchAppliancePolicy управления. Например: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Назначение политики пользователю

Чтобы назначить политику отдельным пользователям, используйте Grant-CsTeamsSurvivableBranchAppliancePolicy управления. Этот cmdlet имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity | Удостоверение пользователя |
| Имя политики | Удостоверение политики |
||

Например:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Вы можете удалить политику пользователя, $Null политику, как показано в следующем примере:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Зарегистрируйте приложение для SBA в Azure Active Directory

Чтобы различные SBAs, используемые в клиенте, могли читать необходимые данные из Microsoft 365, необходимо зарегистрировать приложение для SBA в Azure Active Directory. 

Дополнительные сведения о регистрации приложений см. в следующих сведениях:

- [Разработка бизнес-приложений для Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Зарегистрируйте приложение в платформа удостоверений Майкрософт](/azure/active-directory/develop/quickstart-register-app).  

Вам нужно зарегистрировать только одно приложение для использования всеми SBAs в клиенте. 

Для регистрации SBA необходимы следующие значения: 

- ИД приложения (клиента) 
- Секрет клиента 

Для приложения SBA помните следующее: 

- Имя может быть любым, что вы решаете.  
- Поддерживаемые типы учетных записей = Учетная запись только в этом организационном каталоге. 
- Uri перенаправления в Интернете = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Неявные маркеры предоставления = маркеры доступа и маркеры ИД. 
- API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.
- Секрет клиента: вы можете использовать любое описание и срок действия. 
- Не забудьте скопировать секрет клиента сразу после его создания. 
- На вкладке Обзор отображается ИД приложения (клиента).

Затем выполните указанные далее действия.

1. Зарегистрируйте приложение.
2. Установите неявные маркеры предоставления.
3. Настройка разрешений API.
4. Создайте секрет клиента.


## <a name="session-border-controller-configuration"></a>Настройка контроллера границы сеанса 

Пошаговая инструкция по настройке геймпада границы сеанса с помощью внедренного ветвного устройства с возможностью ветвей с возможностью ветвей с возможностью ветвячих устройств см. в документации, предоставленной поставщиком SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Ленты](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Отчеты о проблемах

Сообщить о проблемах в организацию службы поддержки поставщика SBC. Сообщая о проблеме, указать, что у вас установлено устройство ветвной ветви с возможностью ветвей с

## <a name="known-issues"></a>Известные проблемы

- После добавления новых устройств для ветвей с использованием ветвной единицы может потребоваться некоторое время, прежде чем вы сможете использовать их в политиках ветвной ветви.

- Когда вы назначаете пользователю политику "Устройство ветвной ветвной ветви с возможностью ветвей с возможностью ветвей", может потребоваться некоторое время, прежде чем она будет показана в результатах Get-CsOnlineUser. 

- Обратный просмотр номеров для контактов Azure AD не выполняется. 

- SBA не поддерживает параметры переад вызовов. 

- Звонок на экстренный номер, настроенный для динамических экстренных вызовов (E911), не поддерживается.
