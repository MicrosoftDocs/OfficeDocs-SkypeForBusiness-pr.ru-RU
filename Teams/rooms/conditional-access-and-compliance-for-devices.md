---
title: Рекомендации по условному доступу и соответствию требованиям для Комнаты Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Узнайте о рекомендуемых политиках условного доступа и Intune соответствия устройств и рекомендациях по Комнаты Microsoft Teams.
ms.openlocfilehash: e16513a840dadf7a5cabe961a0fbbd9135da9b89
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606548"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Условный доступ и Intune для Комнаты Microsoft Teams

В этой статье приведены требования и рекомендации по использованию политик условного доступа и Intune устройств для Комнаты Microsoft Teams, используемых в общих пространствах.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

## <a name="requirements"></a>Требования

Комнаты Teams уже должны быть развернуты на устройствах, которым необходимо назначить политики условного доступа. Если вы еще не развернули Комнаты Teams, см. дополнительные сведения о создании учетных записей ресурсов для комнат и общих устройств [Teams](with-office-365.md) и развертывании Комнаты Microsoft Teams [в Android](../devices/collab-bar-deploy.md).

Для использования условного доступа требуется план обслуживания Azure Active Directory P1. Он входит в лицензию Комнаты Microsoft Teams лицензии.

## <a name="teams-rooms-conditional-access-best-practices"></a>Комнаты Teams условного доступа

Политики условного доступа могут защитить процесс входа на устройствах, которые находятся в общих пространствах и используются несколькими пользователями. Общие сведения об условном доступе в Azure Active Directory (Azure AD) см. в статье "Что такое условный доступ [в Azure Active Directory?"](/azure/active-directory/conditional-access/overview).

При использовании условного доступа для защиты Комнаты Teams учитывайте следующие рекомендации.

-   Чтобы упростить развертывание и управление, включите все учетные записи ресурсов комнаты Microsoft 365, связанные с Комнаты Teams в одну группу пользователей.

-   У вас есть стандарт именования для всех учетных записей Комнаты Teams ресурсов. Например, имена учетных записей mtr-room1@contoso.com и mtr-room2@contoso.com начинаются с префикса mtr-.
    При стандартизации имен учетных записей можно использовать динамические группы в Azure AD для автоматического применения политик условного доступа ко всем этим учетным записям одновременно. [Дополнительные сведения о динамических группах](/azure/active-directory/enterprise-users/groups-dynamic-membership) см. в разделе "Правила для динамического членства в группах".

Список поддерживаемых назначений условного доступа для Комнаты Teams см. в разделе "Поддерживаемые политики [условного доступа"](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Пример политики условного доступа

В приведенном ниже примере политика условного доступа работает следующим образом:

1.  Учетная запись, которая входит в систему, должна быть членом определенной группы пользователей, в данном примере — группы "Общие устройства".

2.  Учетная запись, которая выполняет вход, должна пытаться получить доступ только к Exchange Online, Microsoft Teams или SharePoint Online. Попытки входа в любое другое клиентское приложение будут отклонены.

3.  Учетная запись ресурса должна выполнять вход на платформе устройств Windows.

4.  Учетная запись ресурса также должна войти из известного надежного расположения.

Если эти условия выполняются успешно и пользователь вводит правильное имя пользователя и пароль, учетная запись ресурса выполнит вход в Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Условный доступ с Microsoft Intune для Комнаты Teams

Требования к соответствию — это определенные правила, которые должны соответствовать устройствам, чтобы они были помечены как соответствующие требованиям, например минимальная версия операционной системы. Устройства должны считаться соответствующими, прежде чем их можно будет использовать для входа в учетную запись ресурса.

Список поддерживаемых политик соответствия Intune для Комнаты Teams см. в разделе "Поддерживаемые [политики соответствия устройств"](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Дополнительные сведения о настройке Intune с устройствами Android в Teams см. в Intune для регистрации устройств [На основе Teams android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Пример (только для Windows): условный доступ с Intune устройства

В этом примере для Комнаты Teams Windows

1. Требуется, чтобы брандмауэр был запущен на Комнаты Teams Windows.

2. Требовать, чтобы Microsoft Defender был запущен на Комнаты Teams.

3. Если комната Teams не соответствует ни одному из этих требований, она не будет помечена как совместимая и устройства не будут входить в систему.

Эта политика соответствия требованиям применяется ко всем пользователям, а не только к учетным записям ресурсов Teams.
