---
title: Планирование автоспутника Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Обзор использования автоспутника Cloud с Skype для бизнеса Server 2019 г.
ms.openlocfilehash: 832ba7fc5e93a76cc3e05d09baecd880241f6c46
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857086"
---
# <a name="plan-cloud-auto-attendants"></a>Планирование автосекретарей в облаке

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Автоспутник, используемый Exchange единой системы обмена сообщениями (Exchange Server 2013 или Exchange Server 2016 г.), больше не доступен в Exchange Server или Exchange Online. Если реализация Skype для бизнеса Server 2019 будет интегрирована с любой из этих Exchange версий, необходимо использовать функции облачного голоса в Интернете, связанные с телефонная система. Сведения о переносе Skype для бизнеса Server и [Exchange Server](plan-um-migration.md) 2013 и 2016 г. см. в Exchange о перемещении служб um Exchange на сервере 2013 и 2016 г. в облако.

Это по сути означает, что вы будете иметь гибридную реализацию Skype для бизнеса Server 2019, если вы хотите использовать унифицированные функции обмена сообщениями, такие как автоспутники. Сведения о настройке гибридного подключения между Skype для бизнеса Server [и Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)

Автоспутник — это облачная служба, которая принимает вызовы клиентов и воспроизводит приветствия, предоставляет им параметры меню и взаимодействует с звонителями с помощью речи или на панели набора телефонов, чтобы перенаправление звонков в нужное место. Каждому автопроизводитесу назначена учетная запись ресурса *(см.* в статью Настройка учетных записей [ресурсов)](configure-onprem-ra.md)в системе Skype для бизнеса Server 2019 г., которая будет напрямую связана с автоспутником в центре администрирования Microsoft Teams администратора. Дополнительные [подробности о](/microsoftteams/create-a-phone-system-auto-attendant) том, что такое автосерсервы и какие варианты и функции существуют для автоспутников, см. в этой статье.

> [!NOTE]
> Автоспутнику можно назначить несколько номеров служб Майкрософт, номера прямой маршрутки или гибридные номера.

Входящий вызов автоспутнику Cloud может занять один из нескольких путей, как показано здесь:

![Схема для автоспутников.](../../SfBServer2019/media/AA-plan-concept.png)

1. Via Skype для бизнеса Server 2019
2. С помощью [пограничного контроллера сеанса](/microsoftteams/direct-routing-border-controllers) [и прямого маршрутинга](/microsoftteams/direct-routing-plan-media-bypass).
3. С помощью номера, домашнего онлайн в Microsoft 365 или Office 365.

См. также:

- [Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)
- [Автоматический ответ и маршрутизация для входящих вызовов](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Requirements

Следующие требования предполагают, что вы уже Skype для бизнеса Server 2019 году в поддерживаемой топологии.  Ваши требования зависят от сценария:

- Если вы уже используете Exchange или локальной системы электронной системы и обновляете ее до Skype для бизнеса 2019 г., вам потребуется зафиксировать структуру автоспутников и повторно создать их в облаке с помощью автоспутников Cloud. Дополнительные сведения см. в Exchange автоматической Exchange или очереди вызова [в телефонная система.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Для новой конфигурации автоспутников Cloud выполните действия, описанные в  [настройках учетных](configure-onprem-ra.md)записей ресурсов.

В дополнение к вышеуказанным требованиям необходимо настроить ниже требования для подключения к службе автосервиса Microsoft Cloud:

- Гибридное подключение. Если вы уже Skype для бизнеса Server и хотите включить автоспутник Cloud для локального пользователя, необходимо убедиться, что между локальной и сетевой средами установлена гибридная связь. Иногда это называется разделенной конфигурацией домена.

   Дополнительные сведения см. в Skype для бизнеса Server и Microsoft 365 или [Office 365](plan-hybrid-connectivity.md) и настройка гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365](configure-hybrid-connectivity.md).

- Если автоспутнику назначается номер телефона, вам потребуется лицензия Office 365 корпоративный [E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Создайте [учетную запись веб-ресурса](/MicrosoftTeams/manage-resource-accounts) или учетную запись локального ресурса для каждого автоспутника и назначьте номера телефонов и лицензии. [](configure-onprem-ra.md) 

## <a name="migration-and-interoperability"></a>Миграция и интероперабельность

Если планируется развертывание Skype для бизнеса Server 2019 и Exchange Server 2019 г., необходимо тщательно планировать миграцию, чтобы обеспечить поддержку автоспутников. Учитывайте следующее:

- Exchange Server 2019 г. больше не предоставляет Exchange функций um
- Exchange Единая система обмена сообщениями находится в режиме выхода на пенсию
- Skype для бизнеса Server 2019 г. больше не интегрируется с Exchange Online системы

Облачные автовласти можно настроить с Skype для бизнеса Server 2019, 2015 и 2013 годов.

Корпорация Майкрософт рекомендует следующие пути миграции:

- Если вы обновляете Skype для бизнеса Server 2019 г., вы можете использовать Exchange um в Exchange Server 2013 или 2016 гг., но при использовании Exchange Server 2019 г. необходимо перейти на автосерврач Cloud.

- Если вы обновляете Exchange Server 2019 г. и используете предыдущие версии Exchange Server обмена сообщениями Skype для бизнеса Server голосовых сообщений, Корпорация Майкрософт рекомендует обновиться до Skype для бизнеса Server 2019 г. до обновления почтовых ящиков.  В противном случае возможности голосовой передачи сообщений будут потеряны.

Дополнительные сведения о планировании миграции см. в Skype для бизнеса Server [и Exchange Server миграции.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Перенос ранее реализованной Exchange системы автопоследников системы um

В настоящее время мы не поддерживаем автоматическую миграцию в облако системы автопоследников um, созданной в Exchange 2013 или 2016 годах. Чтобы вручную создать систему автоотвода, необходимо:

1. Используйте Exchange команд администратора PowerShell, чтобы просмотреть структуру старой системы автоспутников, включая все вложенные автоспутники и очереди вызовов.  
2. Создание копий сценариев от текста к речи или записанных сообщений, связанных с каждым узлом автосерсерватора um.
3. Создайте конечные точки для каждого узла автопопутника, включая назначение объектов тестовых номеров телефонов и лицензий. Обратите внимание, что теперь у вас есть возможность назначить локальное лицензирование номеров телефонов, используемых сетевыми службами, например телефонная система.
4. Внедрение новой службы автоконцерна Cloud с Microsoft Teams и телефонная система. Сведения [о реализации см. в](configure-onprem-ra.md) перенастройке учетных записей ресурсов. При этом загрузите скрипты с текстом на речь или записанные сообщения, связанные с каждым узлом автосерсерватора um.
5. Проверьте функциональность автобомки Cloud.
6. Перенастройка номера телефона, назначенного старой Exchange автоспутнику um, вновь созданному главному автопроводнику Cloud.

Дополнительные [сведения об этих действиях см. в Exchange](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) автоматического помощника по телефонная система или очереди вызова.

Если у вас есть твердая структура, которая отвечает вашим потребностям, и скрипт, который эффективно направляет клиентов, перенастройте учетные записи [ресурсов.](configure-onprem-ra.md)

> [!CAUTION]
> Как упоминалось в [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)перемещение Exchange автоматических помощников, созданных в Server 2015, на серверы под управлением Server 2019, не рекомендуется. В настоящее время их необходимо хранить в пуле Skype для бизнеса Server 2015 г. в режиме сосуществования.

## <a name="see-also"></a>См. также

[Планирование миграции Skype для бизнеса Server и Exchange Server](plan-um-migration.md)

[Настройка учетных записей ресурсов](configure-onprem-ra.md)

[Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Что представляют собой облачные автосекретари?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange М.М.: [Автоматически отвечать на входящие вызовы и маршрут](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](plan-hybrid-connectivity.md)

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](configure-hybrid-connectivity.md)

[KB4480742: вызовы в абонентский доступ или автоспутник не удается с быстрой загруженности и "500 сервер внутренних" ошибки после перемещения контактных объектов в Skype для бизнеса Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
