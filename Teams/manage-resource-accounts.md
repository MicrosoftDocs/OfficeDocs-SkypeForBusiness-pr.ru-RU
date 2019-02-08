---
title: Управление учетными записями ресурсов в группах
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Управление учетными записями ресурсов в группах Майкрософт
ms.openlocfilehash: 53d335b4f345967494767445ec206efcb6f78388
ms.sourcegitcommit: e091201f2bcb86bee011e7ac0de741a6c673cedd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "29770718"
---
# <a name="manage-resource-accounts-in-teams"></a>Управление учетными записями ресурсов в группах 

Учетная запись ресурса также называется объект отключенных пользователей в Azure Active Directory и может использоваться для представления ресурсов в целом. В Exchange он может использоваться для представления конференц-залы, например и разрешать им номер телефона. Учетная запись ресурса может быть размещен в Microsoft 365 или локально с помощью Скайп for Business server, и эти учетные записи создаются с помощью команды Powershell.

В ОС группами Майкрософт Скайп для бизнеса в Интернет, каждого вызова очередь или auto attendant необходимо иметь учетной записи связанных ресурсов. Должна ли учетная запись ресурса на номер телефона, назначенный зависят от целям использования очереди связанного звонка или принимаемые автосекретарем. Можно найти в статьях в очередь вызова и автосекретарей связанных в нижней части в этой статье перед назначением номер телефона для учетной записи ресурса.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Необходимые условия для назначения номера телефона для учетной записи ресурса

Для начала работы необходимо помнить следующее:
  
- Ваша организация должна иметь (как минимум) лицензию типа "Корпоративный E3 с**телефонной системой"** или лицензию "Корпоративный E5". Число пользовательских лицензий **Телефонной системой** , для которых влияет на число номеров службы, которые доступны для использования для учетных записей ресурсов, назначенных для вызова очередей или автосекретарей. Число учетных записей ресурсов, которые могут возникнуть, зависит от числа лицензий **Телефонной системой** и **Звук конференц-связи** , назначенные в вашей организации. Дополнительные сведения о лицензировании видеть [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Для перенаправления вызовов тем сотрудникам организации, которые находятся в сети, им необходимо предоставить лицензию на **телефонную систему** и разрешить доступ к корпоративной голосовой связи, либо предоставить тарифные планы Office 365. В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Для предоставления сотрудникам доступа к корпоративной голосовой связи, можно использовать Windows PowerShell. Например, выполните:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Чтобы больше узнать о тарифных планах Office 365, см. [Что представляют собой тарифные планы в Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) и [Тарифные планы для Office 365](/microsoftteams/calling-plans-for-office-365).
- Можно назначить только международную и бесплатных служба телефонных номеров, для которого в **Центр администрирования группами Майкрософт** или передан от другого поставщика услуг в учетную запись ресурса. Чтобы получить и использовать бесплатные телефонные номера, необходимо настроить кредиты на услуги связи.

> [!NOTE]
> Номера телефонов пользователей (подписчика) не может быть назначен учетная запись ресурса - можно использовать только службы международную и бесплатных номеров телефонов.

Чтобы назначить учетную запись ресурса номер телефона, необходимо получить или перенос существующих международную или бесплатная служба номеров. После получения счета или бесплатная служба телефонных номеров, они будут отображаться в **центре администрирования группами Майкрософт** > **голосовой связи** > **номера телефонов**и **тип номера** в списке будет отображаться как **Служба — бесплатный номер**. Чтобы получить номер службы, просмотреть [номера телефона службы Приступая к](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) или существующий номер службы и передача, см [передачи телефонных номеров в Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Если вы находитесь за пределами США, не могут использовать Центр администрирования группами Майкрософт для получения номера службы. Перейдите на [Управление телефонные номера для вашей организации](/microsoftteams/manage-phone-numbers-for-your-organization) вместо этого на вашу за ее пределами США.

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

[Планирование облачных автосекретаря](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant.md)

[Настройка автосекретарей облако](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant.md)

Для реализации в группы или Скайп для бизнеса в Интернет:

[Что такое автосекретари телефонной системы?](what-are-phone-system-auto-attendants.md)

[Настройка автосекретаря телефонной системы](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md)

[Пример для малого бизнеса — Настройка автосекретарю.](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Создание очереди звонков в телефонной системе](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue.md)

[Новый CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Новый CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)