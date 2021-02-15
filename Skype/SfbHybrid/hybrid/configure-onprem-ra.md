---
title: Настройка учетной записи ресурса в Skype для бизнеса Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Настройка учетной записи ресурса для Skype для бизнеса Server 2019.
ms.openlocfilehash: 1d8294eb717982b5ac68df06a5370059e83a62c5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919015"
---
# <a name="configure-resource-accounts"></a>Настройка учетных записей ресурсов

Гибридные реализации Skype для бизнеса Server 2019 используют только облачные службы, предоставляемые телефонной системой, для единой системы обмена сообщениями и не интегрируются с Exchange Online. In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant. Эта учетная запись ресурса может быть опубликована в Интернете (см. статью "Управление учетными записями ресурсов в [Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) для создания учетных записей ресурсов в Интернете") или локально, как описано в этой статье. Обычно у вас будет несколько узлов автоотчета телефонной системы или очереди звонков, каждый из которых сопозовется с учетными записями ресурсов, которые можно использовать в Интернете или в Skype для бизнеса Server 2019.

Если у вас уже есть автозаполнетель и система очередей вызовов Exchange, перед переходом на Exchange Server 2019 или Exchange Online необходимо вручную записать сведения, как описано ниже, а затем реализовать совершенно новую систему с помощью Центра администрирования Teams.

## <a name="overview"></a>Общие сведения

Если автослужбу телефонной системы или очереди звонков потребуется номер службы, различные зависимости могут быть выполнены в следующей последовательности:

1. Получите номер службы.
2. Получите бесплатную лицензию "Телефонная система — [виртуальный пользователь"](/MicrosoftTeams/teams-add-on-licensing/virtual-user) или платную лицензию на телефонную систему для использования с учетной записью ресурса.
3. Создайте учетную запись ресурса. Для автоотчета или очереди вызовов требуется связанная учетная запись ресурса.
4. Дождись синхронизации Active Directory между интернет-службой и локальной службой.
5. Назначьте лицензию телефонной системы учетной записи ресурса.
6. Назначьте номер службы учетной записи ресурса.
7. Создайте очередь вызовов телефонной системы или автоотвессник.
8. Соотносим учетную запись ресурса с автоотчетом или очередью вызовов: (New-CsApplicationInstanceAssociation).

Если автоотчет или очередь звонков вложены в автоотчет верхнего уровня, связанной учетной записи ресурса требуется только номер телефона, если требуется несколько точек входа в структуру автоотчетников и очередей вызовов.

Чтобы перенаправлять звонки людям в вашей организации,  которые находятся в Сети, им необходимо иметь лицензию на телефонную систему и иметь разрешение на Корпоративная голосовая связь или планы звонков Microsoft 365 или Office 365. См. ["Назначение лицензий Microsoft Teams".](/MicrosoftTeams/assign-teams-licenses) Чтобы включить их для Корпоративная голосовая связь, можно использовать Windows PowerShell. Например, запустите:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Если создаваемая очередь вызовов или автоспутница телефонной системы будут вложены и не потребуется номер телефона, процесс будет:

1. Создание учетной записи ресурса  
2. Ожидание синхронизации Active Directory между интернет-службой и локальной службой
3. Создание автоспутника телефонной системы или очереди звонков
4. Связывать учетную запись ресурса с автоконтарем телефонной системы или очередью звонков

## <a name="create-a-resource-account-with-a-phone-number"></a>Создание учетной записи ресурса с номером телефона

Создание учетной записи ресурса, использующей номер телефона, потребует выполнения следующих задач в следующем порядке:

1. Порт или получите платный или бесплатный номер службы. Номер не может быть назначен другим голосовым службам или учетным записям ресурсов.

   Прежде чем назначать номер телефона учетной записи ресурса, необходимо получить или переназначить существующие платные или бесплатные номера служб. После получения платных или бесплатных номеров телефонов службы они покажутся на номерах голосовых телефонов Центра администрирования **Microsoft Teams,** а указанный тип номера будет указан как  >    >   **"Служба — бесплатный".**  Чтобы получить номера служб, см. статью "Получение номеров телефонов службы" или "Перенос существующих номеров служб" в статью "Передача номеров телефонов [в Teams".](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams) [](/MicrosoftTeams/getting-service-phone-numbers)

   Если вы находитесь за пределами США, вы не можете использовать Центр администрирования Microsoft Teams для получения номеров служб. Перейдите [в управление номерами](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) телефонов для вашей организации, чтобы узнать, как это сделать из-за пределов США.

2. Купить лицензию на телефонную систему. См. следующие статьи:  
   - [Телефонная система — лицензия виртуального пользователя](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 корпоративный E1 и E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 корпоративный E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Программное обеспечение Office 365 корпоративный E5 бизнес](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Создайте учетную запись локального ресурса, задав для каждой из них имя, SIP-адрес и так далее, задав каждому из них `New-CsHybridApplicationEndpoint` имя, SIP-адрес и так далее.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Дополнительные сведения об этой команде см. в командной точке [New-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

4. (Необязательно) После создания учетных записей ресурсов можно дождаться синхронизации AD между интернет-и локальной системами или принудительно синхронизироваться и перейти к настройке автоотчета телефонной системы или очередей звонков. Чтобы принудительно выполнить синхронизацию, необходимо выполнить следующую команду на компьютере с AAD Connect (если вы еще не сделали этого, потребуется загрузить для запуска `import-module adsync` команды):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Дополнительные сведения об этой команде см. в [start-ADSyncSyncCycle.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)
    
    Обратите внимание, что на этом этапе учетная запись может синхронизироваться, но подготовка может быть не завершена.  Проверьте выходные данные [get-CsOnlineApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)  Если синхронизированная конечная точка еще не завершила подготовка, она не будет отображаться здесь.  Состояние запросов на предоставление можно проверить на портале M365 в состоянии [установки Teams.](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)  Этот этап подготовка может занять до 24 часов.

5. Назначьте учетной записи ресурса лицензию "Телефонная система — виртуальный пользователь" или "Телефонная система". См. ["Назначение лицензий](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) на надстройки Microsoft Teams" и "Назначение [лицензий пользователям".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

   Если вы назначаете номер телефона учетной записи ресурса, вы можете использовать бесплатную лицензию "Телефонная система — виртуальный пользователь". Это обеспечивает возможности телефонной системы для телефонных номеров на уровне организации и позволяет создавать функции автоотправления и очереди звонков.


6. Назначьте номер службы учетной записи ресурса. Используйте `Set-CsHybridApplicationEndpoint` команду, чтобы назначить номер телефона (с параметром -LineURI) учетной записи ресурса.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Дополнительные сведения об этой команде см. в командной точке [Set-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps)

    Чтобы назначить учетной записи ресурса прямую маршрутику или гибридный номер, используйте следующий cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   Учетной записи ресурса потребуется соответствующий номер телефона, если он будет назначен автоотчету верхнего уровня или очереди звонков. Учетной записи ресурса не могут быть назначены номера телефонов пользователей (подписчиков), можно использовать только платные или бесплатные номера телефонов служб.

     Учетной записи ресурса можно назначить прямую маршрутику или гибридный номер. Подробные сведения см. в сведениях о планировании [прямой маршрутки](/MicrosoftTeams/direct-routing-plan) и [планировании облачных автоотправок.](plan-cloud-auto-attendant.md)

     > [!NOTE]
     > Номера служб прямой маршрутки, присвоенные учетным записям ресурсов для автоотчета и очередей вызовов, поддерживаются только для пользователей и агентов Microsoft Teams.

7. Создайте автоспутник телефонной системы или очередь звонков. Выберите один из указанных ниже вариантов.

   - [Настройка облачного автосекретаря](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Создание облачной очереди вызовов](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Связать учетную запись ресурса с выбранным ранее автоотчетом или очередью вызовов телефонной системы.

## <a name="create-a-resource-account-without-a-phone-number"></a>Создание учетной записи ресурса без номера телефона

В этом разделе обсуждается создание локальной учетной записи ресурса. Создание учетной записи ресурса, которая находится в Интернете, обсуждается на веб-сайте "Управление учетными записями [ресурсов" в Microsoft Teams.](/MicrosoftTeams/manage-resource-accounts)

Эти действия необходимы независимо от того, создаете ли вы совершенно новую структуру автозахватаря телефонной системы или очереди звонков, или структуру перестроения, изначально созданную в единой системе обмена данными Exchange.

Войдите на сервер переднего сервера Skype для бизнеса и запустите следующие cmdlets PowerShell:

1. Создайте учетную запись локального ресурса, задав для каждой из них имя, SIP-адрес и так далее, задав каждому из них `New-CsHybridApplicationEndpoint` имя, SIP-адрес и так далее.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Дополнительные сведения об этой команде см. в командной точке [New-CsHybridApplicationEndpoint.](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

2. (Необязательно) После создания учетных записей ресурсов можно дождаться синхронизации AD между интернет-и локальной системами или принудительно синхронизироваться и перейти к настройке автоотчета телефонной системы или очередей звонков. Чтобы принудительно выполнить синхронизацию, необходимо выполнить следующую команду на компьютере с AAD Connect (если вы еще не сделали этого, потребуется загрузить для запуска `import-module adsync` команды):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Дополнительные сведения об этой команде см. в [start-ADSyncSyncCycle.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler)

3. Создайте автоспутник телефонной системы или очередь звонков. Выберите один из указанных ниже вариантов.
   - [Настройка облачного автосекретаря](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Создание облачной очереди вызовов](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Соотнося учетную запись ресурса с автоотчетом телефонной системы или выбранной ранее очередью звонков.

## <a name="test-the-implementation"></a>Тестирование реализации

Лучший способ проверить реализацию — вызвать номер, настроенный для автозапуска телефонной системы или очереди вызовов, и подключиться к одному из агентов или меню. Вы также можете быстро отправить тестовый вызов с помощью кнопки **"Тестирование"** в области действий Центра администрирования. Если вы хотите внести изменения в автоконтаря или очередь вызовов телефонной системы, выберите его и нажмите кнопку "Изменить" в области **действий.** 

> [!TIP]
> Если у вашей учетной записи ресурса возникают трудности с присвоением очереди [](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) вызовов или автосчетщику, см. раздел "Известные проблемы с [Microsoft Teams"](/MicrosoftTeams/Known-issues#phone-system) и раздел "Устранение гибридных экземпляров приложений" в блоге Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Перемещение автоспутника или очереди вызовов exchange в телефонную систему

Для миграции из системы обмена данными Exchange в телефонную систему потребуется повторное воссоздание очереди вызовов и структуры автозахваждения, прямой перенос с одного на другой не поддерживается. Для повторной реализации набора очередей вызовов и автоспутников:

1. Чтобы получить список всех автозаетарях и очередях вызовов exchange, вызовите следующую команду в системе Exchange 2013 или 2016 во время входа в систему от имени администратора:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Для каждой из перечисленных очередей вызовов или автозахватаря exchange следует отметить ее место в структуре, параметрах и получить копии связанных звуковых или текстовых файлов (guid в выходных данных будет именем папки, в которой хранятся файлы). Эти сведения можно получить с помощью команды:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Дополнительные сведения об этой команде см. в командной команде [Get-UMAutoAttendant.](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) Полный список параметров, которые вам может потребоваться захватить, находится в членах [UMAutoAttendant,](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) но наиболее важные из них:

    - Рабочие часы
    - Не-часы
    - Язык
    - Расписание праздников.

3. Создайте новые конечные точки локально, как описано выше.
   В целях тестирования назначьте автоотводу верхнего уровня временный номер.

4. Настройте автоспутник телефонной системы или очередь звонков, использующую конечные точки, как описано выше.

5. Протестировать автоотвод или очередь вызовов телефонной системы.

6. Перенастройка телефонного номера, связанного с очередью вызовов или автозахватарем exchange, соответствующему автоотводу или очереди вызовов телефонной системы.  

   На этом этапе, если голосовая почта уже перенесена, необходимо перейти на Exchange Server 2019.

## <a name="see-also"></a>См. также

[Создание облачной очереди вызовов](/MicrosoftTeams/create-a-phone-system-call-queue)

[Что представляют собой облачные автосекретари?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Настройка облачного автосекретаря](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Планирование автосекретарей в облаке](plan-cloud-auto-attendant.md)

[Планирование очередей звонков в облаке](plan-call-queue.md)

[Планирование облачной службы голосовой почты для пользователей локальной сети](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Управление учетными записями ресурсов в Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( создание учетных записей ресурсов, которые можно найти в Интернете\)
