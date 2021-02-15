---
title: Планирование облачного автоспутника
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Обзор использования облачного автоотвода со Skype для бизнеса Server 2019
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918695"
---
# <a name="plan-cloud-auto-attendants"></a>Планирование автосекретарей в облаке

Автоотвод, используемый с единой системы обмена сообщениями Exchange (Exchange Server 2013 или Exchange Server 2016), больше не доступен в Exchange Server 2019 или Exchange Online. Если ваша реализация Skype для бизнеса Server 2019 интегрируется с любой из этих версий Exchange, необходимо использовать функции облачной голосовой связи в Интернете, связанные с телефонной системой. Сведения о перемещении служб exchange UM, которые на сервере Exchange Server 2013 и [2016, в](plan-um-migration.md) облако см. в планировании миграции Skype для бизнеса Server и Exchange Server 2016.

Изначально это означает, что если вы хотите использовать функции единой системы обмена сообщениями, например автоотвещающие, вы будете использовать гибридную реализацию Skype для бизнеса Server 2019. См. сведения о настройке гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)

Автоответчик — это облачная служба, которая принимает вызовы клиентов и воспроизводит приветствия, предоставляет им параметры меню и взаимодействует с звонющими с помощью речи или панели набора номера, чтобы перенаправление вызовов в нужное место назначения. Каждому автоотчетщику  назначена учетная запись ресурса (см. статью "Настройка учетных записей [ресурсов")](configure-onprem-ra.md)в системе Skype для бизнеса Server 2019, которая будет связана непосредственно с автоотчетом в Центре администрирования Microsoft Teams. Дополнительные [вопросы о](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) том, что такое автоотвечающие, а также какие параметры и функции существуют для автоотводов, см. в этой теме.

> [!NOTE]
> Автослужбу можно назначить несколько номеров служб Майкрософт, номеров прямой маршрутки или гибридных номеров.

Входящий вызов облачного автоотвода может проходить по одному из нескольких путей, как показано ниже:

![Схема для автоспутников](../../SfBServer2019/media/AA-plan-concept.png)

1. Через Skype для бизнеса Server 2019
2. Через [пограничный контроллер сеансов](/MicrosoftTeams/direct-routing-border-controllers.md) и [прямую маршрутику](/MicrosoftTeams/direct-routing-plan.md)
3. Через номер, который можно в Интернете в Microsoft 365 или Office 365.

См. также:

- [Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)
- [Автоматический ответ и маршрутизация для входящих вызовов](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requirements

В следующих требованиях предполагается, что skype для бизнеса Server 2019 уже развернут в поддерживаемой топологии.  Ваши требования зависят от сценария:

- If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants. Дополнительные сведения см. в сведениях о перемещении автоотвода или очереди [вызовов exchange в телефонную систему.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Для новой конфигурации облачных автоотчетников выполните действия, описанные в настройке учетных записей [ресурсов.](configure-onprem-ra.md)

Помимо перечисленных выше требований, для подключения к службе автослужба Microsoft Cloud необходимо настроить перечисленные ниже требования.

- Гибридное подключение. Если у вас уже развернут Skype для бизнеса Server, и вы хотите включить облачный автоспутник для своих пользователей в локальной среде, необходимо убедиться, что между локальной и сетевой средами настроено гибридное подключение. Такая конфигурация иногда называется конфигурацией разделенного домена.

   Дополнительные сведения см. в сведениях о планировании гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365](plan-hybrid-connectivity.md) и настройке гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)

- Если вы назначаете номер телефона автомобилю, вам потребуется лицензия [на Office 365 корпоративный E5.](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)
- Создайте [учетную запись интернет-ресурса](/MicrosoftTeams/manage-resource-accounts.md) или учетную запись локального ресурса для каждого автоотчета и назначьте номера телефонов и лицензии. [](configure-onprem-ra.md) 

## <a name="migration-and-interoperability"></a>Миграция и взаимозаменяемость

Если планируется развертывание Skype для бизнеса Server 2019 и(или Exchange Server 2019), необходимо тщательно спланировать миграцию, чтобы обеспечить поддержку автосохранеников. Учитывайте следующее:

- Exchange Server 2019 г. больше не предоставляет функции exchange UM
- Единая система обмена сообщениями Exchange находится в режиме выхода из системы
- Skype для бизнеса Server 2019 больше не интегрируется с exchange Online UM

Облачные автозаверяющие могут быть настроены в Skype для бизнеса Server 2019, 2015 и 2013.

Корпорация Майкрософт рекомендует следующие пути миграции:

- При обновлении до Skype для бизнеса Server 2019 можно использовать exchange UM в Exchange Server 2013 или 2016, но при использовании Exchange Server 2019 необходимо перейти на облачный автоспутник.

- При обновлении до Exchange Server 2019 и использовании предыдущих версий системы обмена сообщениями Exchange Server для голосовых сообщений Skype для бизнеса Server корпорация Майкрософт рекомендует обновить систему до Skype для бизнеса Server 2019 перед обновлением почтового ящика.  В противном случае возможности голосовой почты будут потеряны.

Дополнительные сведения о планировании миграции см. в сведениях о планировании миграции Skype для бизнеса [Server и Exchange Server миграции.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Миграция ранее реализованной системы автообсветаря exchange UM

В настоящее время мы не поддерживаем автоматическую миграцию в облако системы автозахватаря, созданной в Exchange 2013 или 2016. Чтобы вручную повторно создать систему автоотвода, необходимо:

1. С помощью команд PowerShell администратора Exchange просмотрите структуру старой системы автозахватаря, в том числе вложенные автоспутники и очереди вызовов.  
2. Создайте копии текстовых сценариев или записанных сообщений, связанных с каждым узлом автозахватаря системы.
3. Создайте конечные точки локально для каждого узла автозахватаря, включая назначение тестовых номеров телефонов и лицензий объектам. Обратите внимание, что теперь у вас есть возможность назначать лицензии на номера телефонов, используемые веб-службами, например телефонной системой.
4. Реализация новой облачной службы автослужб с Помощью Microsoft Teams и телефонной системы. Сведения [о реализации](configure-onprem-ra.md) см. в подстройке "Настройка учетных записей ресурсов". В этом случае загрузите скрипты или записанные сообщения, связанные с каждым узлом автозахватаря системы.
5. Протестировать функции облачного автоотвода.
6. Перенанастройка номера телефона, назначенного старому автоотводу exchange, только что созданному главному облачному автоспутесу.

Дополнительные [сведения об этих действиях](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) см. в сведениях о перемещении автоотвода или очереди вызовов exchange в телефонную систему.

Если у вас есть надстройка, которая соответствует вашим потребностям, и сценарий, который эффективно направляет клиентов, переходите к настройке учетных записей [ресурсов.](configure-onprem-ra.md)

> [!CAUTION]
> Как упоминалось в [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)не рекомендуется перенастраивать созданные в Сервер 2015 автоотводы exchange на серверы с Сервер 2019. В настоящее время их необходимо оставить в пуле Skype для бизнеса Server 2015, который работает в режиме сосуществования.

## <a name="see-also"></a>См. также

[Планирование миграции Skype для бизнеса Server и Exchange Server](plan-um-migration.md)

[Настройка учетных записей ресурсов](configure-onprem-ra.md)

[Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Что представляют собой облачные автосекретари?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)

Um Exchange: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](plan-hybrid-connectivity.md)

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](configure-hybrid-connectivity.md)

[KB4480742: сбой вызовов абонентского доступа или автоответника при быстрой занятости и ошибке "500 Server Internal" после перемещения контактных объектов в Skype для бизнеса Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
