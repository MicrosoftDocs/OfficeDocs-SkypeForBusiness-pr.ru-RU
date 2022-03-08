---
title: Регистрация устройства Комнаты Teams в управляемой Комнаты Microsoft Teams премиум
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как зарегистрировать Комнаты Microsoft Teams учетные записи в Комнаты Microsoft Teams премиум управляемой службе.
f1keywords: ''
ms.openlocfilehash: d00c4f84447e8ba41f0328cca9b907db45e8fdb7
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070418"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Регистрация устройства в управляемой Комнаты Microsoft Teams премиум службе

Чтобы зарегистрировать устройство Комнаты Microsoft Teams в управляемой службе Комнаты Teams Premium, необходимо назначить одного или нескольких пользователей администратору управляемой службы, а затем выполнить действия по регистрации с помощью этого пользователя.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Назначение пользователей роли "Администратор управляемых служб"

Чтобы назначить пользователям роль администратора управляемой службы, выполните следующие действия:

1. Войдите на Комнаты Teams Premium [с](https://portal.rooms.microsoft.com/) помощью тех же прав администратора, что и для входа в Центр администрирования Microsoft 365.
2. Перейдите **в Параметры** >  **Параметры** >  **В этом оке выберите** **Администратор управляемых служб**.
3. В **области Администратор управляемых служб** выберите **вкладку Задания** , а затем выберите **Добавить**.
4. Следуйте мастеру, чтобы назвать задание, и выберите пользователей, которых нужно добавить в него. Это задание будет применяться для всех комнат и групп помещений.
5. В конце мастера заданий выберите Добавить **задание**.

Пользователи, которым назначена роль администратора управляемой службы, отвечают за ежедневное управление и мониторинг Комнаты Teams Premium портала управляемых служб.

После того как вы настроим для пользователей роль администратора управляемой службы[](enroll-a-device.md), перенаправьсь к функции Зарегистрировать устройство Комнаты Teams, чтобы добавить устройство Комнаты Teams на портал управляемых служб.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
