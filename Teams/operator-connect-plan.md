---
title: Operator Connect
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
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
description: Mer informasjon о Operator Connect, таких как требования и планирование развертывания.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 745587281c5566b1ba4fe0d1ea06a44d40c8a7f2
ms.sourcegitcommit: 5a8a077b30a0eab2342afc422869adaa682a015b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2022
ms.locfileid: "66915187"
---
# <a name="plan-for-operator-connect"></a>Планирование подключения оператора

Operator Connect — это еще один вариант для обеспечения подключения телефонной сети общего пользования (ТСОП) к Teams и телефонной системе. Дополнительные сведения о голосовых решениях Teams и вариантах подключения к ТСОП см. в статье "Планирование голосового решения [Teams](cloud-voice-landing-page.md) и параметров подключения к [ТСОП"](pstn-connectivity.md).

В этой статье описываются преимущества и требования, а также приводятся ссылки на операторов, участвующих в программе Microsoft Operator Connect.  Если вы решили, что Operator Connect является правильным решением для вашей организации, прочитав эту статью, см. раздел ["Настройка operator Connect"](operator-connect-configure.md).  

## <a name="benefits"></a>Преимущества

Если оператор Operator Connect является участником программы Microsoft Operator Connect, он может управлять службой для вызова ТСОП в Teams. Программа Operator Connect предоставляет следующие преимущества:

- **Используйте существующие контракты или найдите новый оператор.** Вы сохраняете предпочитаемый оператор и контракты или выбираете новый из списка участвующих операторов в соответствии с потребностями вашего бизнеса.

- **Инфраструктура, управляемая оператором.** Оператор управляет службами звонков ТСОП и пограничными контроллерами сеансов (SBC), позволяя сэкономить на приобретении оборудования и управлении.

- **Более быстрое и простое развертывание.** Вы можете быстро подключиться к оператору и назначить номера телефонов пользователям из Центра администрирования Teams.

- **Улучшенная поддержка и надежность.** Операторы предоставляют техническую поддержку и соглашения об уровне обслуживания для улучшения службы поддержки, а прямой пиринг на основе Azure создает сетевое подключение "один к одному" для повышения надежности.

## <a name="requirements"></a>Требования

 Operator Connect может быть правильным решением для вашей организации, если:

- План звонков Майкрософт недоступен в вашем географическом расположении.
- Предпочтительный оператор — участник программы Microsoft Operator Connect.
- Вы хотите найти нового оператора для включения звонков в Teams.

Чтобы включить назначения номеров телефонов с помощью Operator Connect, убедитесь, что пользователи:

- Teams Phone с лицензией. Дополнительные сведения см. в статьях "Что такое [телефонная система"](what-is-phone-system-in-office-365.md) и "Назначение пользователям лицензий на надстройки [Teams"](teams-add-on-licensing/assign-teams-add-on-licenses.md).
- В режиме TeamsOnly. Обратите внимание, что пользователь должен находиться в режиме TeamsOnly, а вся организация — нет. Дополнительные сведения см. в статье ["Общие сведения о Microsoft Teams и Skype для бизнеса сосуществование и взаимодействие"](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

Список операторов, участвующих в программе Microsoft Operator Connect Program, а также стран или регионов, в которых доступна их служба, см. в каталоге [Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).
