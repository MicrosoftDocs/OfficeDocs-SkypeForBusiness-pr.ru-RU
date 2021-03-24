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
localization_priority: Normal
ms.collection: ''
description: Обзор использования автоспутника Cloud в Skype для бизнеса Server 2019
ms.openlocfilehash: b144576b3e572137a512881f4bdcd1ab0e06d0ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110355"
---
# <a name="plan-cloud-auto-attendants"></a>Планирование автосекретарей в облаке

Автоспутник, используемый в Exchange Unified Messaging (Exchange Server 2013 или Exchange Server 2016 г.), больше не доступен в Exchange Server 2019 г. или Exchange Online. Если реализация Skype для бизнеса Server 2019 будет интегрирована с любой из этих версий Exchange, вам потребуется использовать функции облачного голоса в Интернете, связанные с телефонной системой. Сведения о перемещении служб Exchange UM на сервере [Exchange](plan-um-migration.md) 2013 и 2016 в облако см. в Exchange Server Skype для бизнеса Server и Exchange Server.

Это по сути означает, что для использования функций единой системы обмена сообщениями, например автоспутников, будет гибридная реализация Skype для бизнеса Server 2019. Подробнее см. в материале Настройка гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)

Автоспутник — это облачная служба, которая принимает вызовы клиентов и воспроизводит приветствия, предоставляет им параметры меню и взаимодействует с звонителями с помощью речи или на панели набора телефонов, чтобы перенаправление звонков в нужное место. Каждому автоспутнику  назначена учетная запись ресурса (см. статью [Настройка](configure-onprem-ra.md)учетных записей ресурсов) в системе Skype для бизнеса Server 2019, которая будет напрямую связана с автоспутником в центре администрирования Microsoft Teams. Дополнительные [подробности](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) о том, что такое автовласти, а также о том, какие параметры и функции существуют для автоспутников, см. в дополнительных подробностях.

> [!NOTE]
> Автоспутнику можно назначить несколько номеров служб Майкрософт, номера прямой маршрутки или гибридные номера.

Входящий вызов автоспутнику Cloud может занять один из нескольких путей, как показано здесь:

![Схема для автоспутников](../../SfBServer2019/media/AA-plan-concept.png)

1. Skype для бизнеса Server 2019
2. С помощью [пограничного контроллера сеанса](/MicrosoftTeams/direct-routing-border-controllers.md) [и прямого маршрутинга](/MicrosoftTeams/direct-routing-plan.md)
3. С помощью номера, домашнего номера в Microsoft 365 или Office 365.

См. также:

- [Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)
- [Автоматический ответ и маршрутизация для входящих вызовов](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>Требования

Следующие требования предполагают, что skype для бизнеса Server 2019 уже развернут в поддерживаемой топологии.  Ваши требования зависят от сценария:

- Если вы уже используете Exchange UM в Интернете или на локальной основе и перенастроите систему Skype для бизнеса 2019, вам потребуется зафиксировать структуру автоспутников и повторно создать их в облаке с помощью автоспутников Cloud. Дополнительные сведения см. в [примере Перемещение автоспутника exchange UM или очереди вызова в телефонную систему.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- Для новой конфигурации автоспутников Cloud выполните действия, описанные в  [настройках учетных](configure-onprem-ra.md)записей ресурсов.

В дополнение к вышеуказанным требованиям необходимо настроить ниже требования для подключения к службе автосервиса Microsoft Cloud:

- Гибридное подключение. Если у вас уже развернут Skype для бизнес-сервера и вы хотите включить автоспутник Cloud для локального пользователя, необходимо убедиться, что между локальной и онлайн-средой установлено гибридное подключение. Иногда это называется разделенной конфигурацией домена.

   Дополнительные сведения см. в веб-сайте Plan [hybrid connectivity between Skype for Business Server и Microsoft 365 или Office 365,](plan-hybrid-connectivity.md) а также настройка гибридного подключения между Skype для бизнеса Server и [Microsoft 365 или Office 365.](configure-hybrid-connectivity.md)

- Если автоспутнику назначается номер телефона, вам потребуется лицензия [Office 365 Enterprise E5.](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)
- Создайте [учетную запись веб-ресурса](/MicrosoftTeams/manage-resource-accounts.md) или учетную запись локального ресурса для каждого автоспутника и назначьте номера телефонов и лицензии. [](configure-onprem-ra.md) 

## <a name="migration-and-interoperability"></a>Миграция и интероперабельность

Если планируется развертывание Skype для бизнеса Server 2019 и/или Exchange Server 2019 г., необходимо тщательно планировать миграцию, чтобы обеспечить поддержку автоспутников. Учитывайте следующее:

- Exchange Server 2019 г. больше не предоставляет функции Обмена обмена данными
- Единая система обмена сообщениями Exchange находится в режиме выхода на пенсию
- Skype для бизнеса Server 2019 больше не интегрируется с Exchange Online UM

Облачные автовласти можно настроить с помощью Skype для бизнеса Server 2019, 2015 и 2013 годов.

Корпорация Майкрософт рекомендует следующие пути миграции:

- При обновлении до Skype для бизнеса Server 2019 вы можете использовать exchange UM в Exchange Server 2013 или 2016 гг., но если вы используете Exchange Server 2019 г., необходимо перейти на облачный автосервер.

- Если вы обновляете Exchange Server 2019 г. и используете предыдущие версии системы обмена сообщениями Exchange Server для голосовых сообщений Skype для бизнеса Server, Корпорация Майкрософт рекомендует перейти на Skype для бизнеса Server 2019 до обновления почтовых ящиков.  В противном случае возможности голосовой передачи сообщений будут потеряны.

Дополнительные сведения о планировании миграции см. в веб-сведениях [Plan for Skype for Business Server и Exchange Server миграции.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>Перенос ранее реализованной системы автоматического сопровождающего обмена данными Exchange

В настоящее время мы не поддерживаем автоматическую миграцию в облако системы автоматической службы обмена данными, созданной в Exchange 2013 или 2016. Чтобы вручную создать систему автоотвода, необходимо:

1. Используйте команды администратора Exchange PowerShell, чтобы просмотреть структуру старой системы автоспутников, включая все вложенные автоспутники и очереди вызовов.  
2. Создание копий сценариев от текста к речи или записанных сообщений, связанных с каждым узлом автосерсерватора um.
3. Создайте конечные точки для каждого узла автопопутника, включая назначение объектов тестовых номеров телефонов и лицензий. Обратите внимание, что теперь у вас есть возможность назначать лицензии на номера телефонов, используемые сетевыми службами, например Phone System.
4. Внедрение новой службы автопроизводиющего облачного обслуживания с помощью Microsoft Teams и телефонной системы. Сведения [о реализации см. в](configure-onprem-ra.md) перенастройке учетных записей ресурсов. При этом загрузите скрипты с текстом на речь или записанные сообщения, связанные с каждым узлом автосерсерватора um.
5. Проверьте функциональность автобомки Cloud.
6. Перенастройка номера телефона, назначенного старому автоспутнику Exchange UM, только что созданному главному автопроводнику Cloud.

Дополнительные [сведения об этих действиях](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) см. в материале Перемещение автоспутника exchange UM или очереди вызова в телефонную систему.

Если у вас есть твердая структура, которая отвечает вашим потребностям, и скрипт, который эффективно направляет клиентов, перенастройте учетные записи [ресурсов.](configure-onprem-ra.md)

> [!CAUTION]
> Как уже упоминалось в [KB4480742,](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)перемещение автоспутников Exchange UM, созданных в Server 2015, на серверы под управлением Server 2019 не рекомендуется. В настоящее время их необходимо хранить в пуле Skype для бизнеса Server 2015, который работает в режиме сосуществования.

## <a name="see-also"></a>См. также

[Планирование миграции Skype для бизнеса Server и Exchange Server](plan-um-migration.md)

[Настройка учетных записей ресурсов](configure-onprem-ra.md)

[Включение записи настраиваемых приглашений с помощью телефонного интерфейса пользователя](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[Что представляют собой облачные автосекретари?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[Настройка облачного автосекретаря](/microsoftteams/create-a-phone-system-auto-attendant)

Система обмена данными Exchange: [автоматически отвечать на входящие вызовы и маршрут](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Планирование гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](plan-hybrid-connectivity.md)

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](configure-hybrid-connectivity.md)

[KB4480742: вызовы к доступу к абоненту или автоспутнику сбой при быстрой загруженности и ошибке "500 Server Internal" после переноса контактных объектов в Skype для бизнеса Server 2019](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)