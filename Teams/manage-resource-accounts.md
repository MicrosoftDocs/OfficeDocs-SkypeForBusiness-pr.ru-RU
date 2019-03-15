---
title: Управление учетными записями ресурсов в Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Управление учетными записями ресурсов в группах Майкрософт
ms.openlocfilehash: dad2ea10f2dbdeb387a74d01fd48ca6de9805a5a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633252"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Управление учетными записями ресурсов в Microsoft Teams

Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом. В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона. Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.

В группами Майкрософт или Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов. Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем. Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.

> [!NOTE]
> Эта статья относится к группам Майкрософт и Скайп для бизнеса в Интернет.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Необходимые условия для назначения номера телефона для учетной записи ресурса

Для начала работы необходимо помнить следующее:
  
- Ваша организация должна иметь (как минимум) лицензию типа "Корпоративный E3 с**телефонной системой"** или лицензию "Корпоративный E5". Число пользовательских лицензий **Телефонной системой** , для которых влияет на число номеров службы, которые доступны для использования для учетных записей ресурсов, назначенных для вызова очередей или автосекретарей. Число учетных записей ресурсов, которые могут возникнуть, зависит от числа лицензий **Телефонной системой** и **Звук конференц-связи** , назначенные в вашей организации. Дополнительные сведения о лицензировании см. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365. В разделе [Назначение групп Майкрософт лицензий](assign-teams-licenses.md). Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell. Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Чтобы узнать больше о вызове планы Office 365, обратитесь к разделу [Вызов планы для Office 365](calling-plans-for-office-365.md).
- Можно назначить только международную и бесплатных служба телефонных номеров, для которого в **Центр администрирования группами Майкрософт** или передан от другого поставщика услуг в учетную запись ресурса. Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.

> [!NOTE]
> Номера телефонов пользователей (подписчика) не могут назначаться учетная запись ресурса. Можно использовать только службы международную и бесплатных номеров телефонов.

Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или перенос существующих международную или бесплатная служба номеров. После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**. Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) или необходимо перенести существующий номер службы, в статье [передачи телефонных номеров в Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы. Перейдите на [Управление телефонные номера для вашей организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) вместо этого на вашу за ее пределами США.

## <a name="create-a-resource-account-in-powershell"></a>Создание учетной записи ресурса в Powershell

 Вам нужно создать учетную запись ресурса, выполнив командлет соответствующие Powershell при необходимости (для одного или нескольких учетных записей ресурсов) и присвойте имя каждой из них и т. д. В данный момент не вариант при создании учетной записи ресурса в центре администрирования группами Майкрософт, но можно изменить номера телефонов и измените вызова очередь или auto attendant назначения для учетной записи ресурса.

В зависимости от того, ли номер телефона расположен через Интернет или локально необходимо подключиться к строке соответствующие Powershell с правами администратора.

- Для создания учетной записи ресурса, размещенный на локальном реализации гибридных (номера телефонов, размещенных на прямой маршрутизации, OPCH и системы CCE) будет использовать [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) .  
- Интернет-версия только для реализации, использующие [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) иметь учетную запись ресурса, который расположен в Интернете.

Ниже приведен пример создания учетной записи ресурса online среды:

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

В разделе [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.

> [!NOTE]
> Можно легко установить номер телефона, с помощью центра администрирования группами Майкрософт, как описано в следующем разделе. Вы также можете использовать `Set-CsOnlineApplicationInstance` команду для назначения номер телефона, чтобы учетная запись ресурса после его первоначального создания как показано:

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

В разделе [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) для получения дополнительных сведений о этой команды.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт

Для управления параметрами учетных записей ресурсов в центре администрирования группами Майкрософт, перейдите к **Параметры масштабе организации**  > **учетные записи ресурса**, выберите учетную запись ресурса, чтобы изменить параметры для и нажмите кнопку **Изменить** . в окне **Изменение учетной записи ресурсов** вы сможете изменить:

- **Отображаемое имя** для учетной записи
- Звонок очередь или автосекретаря, который использует учетную запись
- Номер телефона, назначенная учетной записи

По завершении щелкните **Сохранить**.

## <a name="related-information"></a>Связанные сведения

Для реализации, которые являются гибридное развертывание с Скайп для Business Server:

[Планирование автосекретарей в облаке](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Настройка автосекретарей в облаке](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Для реализации в группы или Скайп для бизнеса в Интернет:

[Что такое автосекретари телефонной системы?](what-are-phone-system-auto-attendants.md)

[Настройка автосекретаря телефонной системы](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Пример для малого бизнеса: настройка автосекретаря](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Создание очереди звонков в телефонной системе](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Новый CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Новый CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
