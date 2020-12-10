---
title: Прямая маршрутизация SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Ознакомьтесь с дополнительными сведениями о прямой маршрутизации, такими как конфигурация, требования к развертыванию, необходимые основные решения для развертывания и рекомендации по маршрутизации голосовой связи.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611793"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Бесперебойно работающее устройство филиала (SBA) для прямой маршрутизации — общедоступная Предварительная версия


> [!NOTE]
> Это общедоступная Предварительная версия.

Иногда сайт клиента, использующий прямую маршрутизацию для подключения к телефонной системе Microsoft, может столкнуться со сбоями в Интернете.

Предполагается, что сайт клиента (филиал) временно не может подключаться к облаку Microsoft с помощью прямой маршрутизации. Тем не менее, интрасеть внутри ветви по-прежнему работает полностью, и пользователи могут подключаться к контроллеру границ сеанса (SBC), обеспечивающему подключение по протоколу PSTN.

В этой статье описано, как использовать бесперебойно работающее устройство филиала (SBA), чтобы система Microsoft Phone System продолжала совершать и принимать вызовы по коммутируемой телефонной сети (PSTN) в случае сбоя.

## <a name="prerequisites"></a>Необходимые компоненты

SBA является распространяемым кодом, предоставленным корпорацией Майкрософт поставщикам SBC, которые затем внедряют код в микропрограмму своего SBCs. 

Чтобы получить последнюю версию встроенного микрокода контроллера границы сеанса с помощью встроенного устройства с бесперебойной подразделением, обратитесь к поставщику SBC. Кроме того, необходимо выполнить указанные ниже действия.

- Необходимо настроить SBC для обхода мультимедиа, чтобы убедиться в том, что в клиенте Microsoft Teams на сайте филиала мультимедиа можно переносить непосредственно с помощью SBC. 

- В ОС SBA VM должна быть включена поддержка TLS 1.2.

## <a name="supported-teams-clients"></a>Поддерживаемые клиенты Teams

Функция SBA поддерживается следующими клиентами Microsoft teams: 

- Классическое приложение Microsoft Teams 

- Microsoft Teams macOS Desktop 

## <a name="how-it-works"></a>Принципы работы

Во время отключения в Интернете клиент Teams должен автоматически переключаться на SBA, а текущие звонки должны продолжаться без перерывов. Пользователю не требуется предпринимать никаких действий. После того как клиент Teams обнаружит, что Интернет и все исходящие звонки будут завершены, клиент вернется в обычный режим работы и подключится к другим службам Teams. SBA отправит собранные записи данных о звонке в облако и журнал звонков будут обновлены таким образом, чтобы эта информация была доступна для проверки администратором клиента. 

Если клиент Microsoft Teams работает в автономном режиме, доступны следующие функции, связанные с вызовом: 

- Совершение КОММУТИРУЕМых звонков через местные SBA/SBC с мультимедиа, передаваемым через SBC.

- Получение звонков по коммутируемой телефонной связи через местные SBA/SBC с мультимедиа, передаваемым через SBC. 

- Удержание и возобновление звонков по КТСОП.

## <a name="configuration"></a>Конфигурация

Чтобы функция SBA работала, клиенту Teams нужно знать, какие SBAs доступны в каждом сайте филиала, и какие SBAs назначены пользователям на этом сайте. Ниже указаны этапы настройки.

1. Создайте SBAs.
2. Создание политики бесперебойной работы филиалов Teams.
3. Назначение политики пользователям.
4. Зарегистрируйте приложение для SBA с помощью Azure Active Directory.

Все настройки осуществляется с помощью командлетов PowerShell в Skype для бизнеса Online. (Центр администрирования Teams пока не поддерживает функцию прямой маршрутизации SBA.) 

(Дополнительные сведения о настройке SBC и ссылки на документацию поставщика SBC см. в разделе Конфигурация контроллера границ сеанса в конце этой статьи.)

### <a name="create-the-sbas"></a>Создание SBAs

Чтобы создать SBAs, вы будете использовать командлет New-CsTeamsSurvivableBranchAppliance. Этот командлет имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity  | Удостоверение SBA  |
| Fqdn | Полное доменное имя SBA |
| Сайт | TenantNetworkSite, где находится SBA |
| Описание | Бесплатный формат текста |
|||

Например:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Создание политики бесперебойной работы филиалов Teams 

Чтобы создать политику, используйте командлет New-CsTeamsSurvivableBranchAppliancePolicy. Этот командлет имеет следующие параметры: Обратите внимание, что политика может содержать один или несколько SBAs.

| Параметр| Описание |
| :------------|:-------|
| Identity | Удостоверение политики. |
| BranchApplianceFqdns  | Полное доменное имя SBA (ов) на сайте |
||

Например:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Вы можете добавить или удалить SBAs из политики с помощью командлета Set-CsTeamsSurvivableBranchAppliancePolicy. Например: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Назначение пользователю политики

Чтобы назначить политику отдельным пользователям, вы будете использовать командлет Grant-CsTeamsSurvivableBranchAppliancePolicy. Этот командлет имеет следующие параметры:

| Параметр| Описание |
| :------------|:-------|
| Identity | Удостоверение пользователя |
| PolicyName | Удостоверение политики. |
||

Например:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Вы можете удалить политику с пользователя, предоставив $Null политику, как показано в следующем примере:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Регистрация приложения для SBA с помощью Azure Active Directory

Чтобы разрешить различным SBAs, используемым в вашем клиенте, чтение необходимых данных из Microsoft 365, необходимо зарегистрировать приложение для SBA с помощью Azure Active Directory. 

Дополнительные сведения о регистрации приложений можно найти в следующих статьях:

- [Разработка бизнес-приложений для Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Зарегистрируйте приложение на платформе Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Только одно приложение должно быть зарегистрировано для использования всеми SBAs в клиенте. 

Для регистрации SBA вам понадобятся следующие значения, созданные регистрацией. 

- Идентификатор приложения (клиента) 
- Секрет клиента 

Если вы хотите, чтобы приложение SBA, имейте в виду следующее: 

- Это имя может быть любым из ваших решений.  
- Поддерживаемые типы учетных записей = учетная запись только в этом организационном каталоге. 
- URI перенаправления веб-сайта = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Неявные токены Grant = маркеры доступа и ИДЕНТИФИКАТОРы маркеров. 
- Разрешения API = клиент Skype и Teams Access — > разрешения на доступ к приложениям > application_access_custom_sba_appliance.
- Секрет клиента: вы можете использовать любое описание и срок действия. 
- Не забудьте скопировать секретный ключ клиента сразу после его создания. 
- Идентификатор приложения (клиент) отображается на вкладке Обзор.

Затем выполните указанные ниже действия.

1. Зарегистрируйте приложение.
2. Задайте неявные токены GRANT.
3. Настройте разрешения API.
4. Создайте секрет клиента.


## <a name="session-border-controller-configuration"></a>Настройка контроллера границ сеанса 

Пошаговые инструкции по настройке контроллера границ сеанса с помощью встроенного устройства с бесперебойной подразделением можно найти в документации, предоставленной вашим поставщиком SBC. 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Вариантов](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [Системы TE](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Вопросы, связанные с отчетами

Сообщите о проблемах в организацию поддержки вашего поставщика SBC. При сообщении об ошибке укажите, что вы настроили работающее устройство филиалов.

## <a name="known-issues"></a>Известные проблемы

- При добавлении новых бесперебойных устройств филиалов может потребоваться некоторое время, прежде чем можно будет использовать их в бесперебойно используемых политиках устройств управления филиалами.

- При назначении пользователю бесперебойной политики филиалов может потребоваться некоторое время, прежде чем SBA будет отображено в выходных данных Get-CsOnlineUser. 

- Обратный просмотр номера в контактах Azure AD не выполняется. 

- SBA не поддерживает параметры переадресации звонков. 

- Совершение экстренного звонка на экстренный номер, настроенный на динамическую видеосвязь (E911), не поддерживается.

- В выходных данных Get-CsOnlineUser показан TeamsBranchSurvivabilityPolicy.
