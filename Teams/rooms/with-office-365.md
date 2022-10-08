---
title: Создание учетных записей ресурсов для комнат и общих устройств Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: В этой статье содержатся сведения о создании учетных записей ресурсов для комнат и общих устройств, включая Комнаты Microsoft Teams, Комнаты Teams Surface Hub и функции "Горячее обслуживание" в Teams.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475501"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Создание и настройка учетных записей ресурсов для комнат и общих устройств Teams

В этой статье содержатся инструкции по созданию учетных записей ресурсов для общих пространств и устройств, а также по настройке учетных записей ресурсов для Комнаты Microsoft Teams в Windows, Комнаты Teams на Android, Комнаты Teams на Surface Hub и на дисплеях Teams с горячим обслуживанием.

Учетные записи ресурсов Microsoft 365 — это почтовые ящики и учетные записи Teams, выделенные для определенных ресурсов, таких как комната или проектор. Эти учетные записи ресурсов могут автоматически отвечать на приглашения на собрания с помощью правил, определяемых при их создании. Например, если у вас есть общий ресурс, например конференц-зал, вы можете настроить учетную запись ресурса для этого конференц-зала, которая будет автоматически принимать или отклонять приглашения на собрания в зависимости от доступности календаря. 

Каждая учетная запись ресурса уникальна для одной Комнаты Microsoft Teams или в Teams отображается реализация горячего технического обеспечения.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> При использовании панелей Microsoft Teams учетная запись Комнаты Teams ресурса входит в Комнаты Teams и связанные панели Teams.

> [!NOTE]
> **Skype для бизнеса** <br><br>
> Если необходимо включить учетную запись ресурса для работы с Skype для бизнеса, см. раздел [Комнаты Microsoft Teams с Skype для бизнеса Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="requirements"></a>Требования

В зависимости от среды для создания учетных записей ресурсов требуется одна или несколько ролей.

|**Среды**|**Необходимые роли**|
|-----|-----|
|Azure Active Directory  <br/> |Глобальный администратор или администратор пользователей  <br/> |
|Active Directory  <br/> |Администраторы Active Directory Enterprise, администраторы домена или имеют делегированные права на создание пользователей. Права синхронизации Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Глобальный администратор или администратор Exchange   <br/> |
|Exchange Server  <br/> |Управление организацией Exchange или управление получателями   <br/> |

Если вы создаете учетные записи ресурсов для Комнаты Teams, имя участника-пользователя должно соответствовать SMTP-адресу учетной записи ресурса. [Ознакомьтесь Комнаты Microsoft Teams требования перед](requirements.md) развертыванием Комнаты Teams.

### <a name="what-license-do-you-need"></a>Какая лицензия вам нужна?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>Создание учетной записи ресурса

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>Настройка свойств почтового ящика

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>Отключение срока действия пароля

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>Назначение лицензии на конференц-зал

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>Дальнейшие действия

### <a name="meeting-policies"></a>Политики собрания

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>Звонки

Нет уникальных требований для включения вызовов с учетными записями ресурсов. Вы включаете учетную запись ресурса для вызова так же, как и обычный пользователь.

> [!NOTE]
> Мы рекомендуем отключить голосовую почту для общих устройств, назначив политику звонков учетным записям ресурсов устройств. Дополнительные сведения см. в разделе "Звонки и [переадресация звонков в Teams](../teams-calling-policy.md) ".

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)

[Развертывание комнат Microsoft Teams](rooms-deploy.md)

[Управление комнатами Microsoft Teams](rooms-manage.md)

[Комнаты Microsoft Teams лицензирования](rooms-licensing.md)
