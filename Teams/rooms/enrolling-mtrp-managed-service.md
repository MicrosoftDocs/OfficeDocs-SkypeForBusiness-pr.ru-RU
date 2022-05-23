---
title: Регистрация устройства Комнаты Teams в управляемой Комнаты Microsoft Teams премиум службе
author: donnah007
ms.author: v-donnahill
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
description: Узнайте, как зарегистрировать учетные записи Комнаты Microsoft Teams в Комнаты Microsoft Teams премиум управляемой службе.
f1keywords: ''
ms.openlocfilehash: c64fcaf6e817eb57be2915f4f7b6d8684f2ae49b
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635460"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Регистрация устройства в управляемой Комнаты Microsoft Teams премиум службе

Чтобы зарегистрировать Комнаты Microsoft Teams в управляемой службе Комнаты Teams Premium, необходимо назначить одного или нескольких пользователей администратору управляемой службы, а затем выполнить действия по регистрации с помощью этого пользователя.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Назначение пользователей роли администратора управляемой службы

Выполните следующие действия, чтобы назначить пользователям роль администратора управляемой службы:

1. Войдите на портал [Комнаты Teams Premium с](https://portal.rooms.microsoft.com/) правами администратора, которые использовались для входа в Центр администрирования Microsoft 365.
2. Перейдите **Параметры** >  **Параметры** >  **Roles**, а затем выберите "**Управляемый администратор служб"**.
3. В **разделе "Администратор управляемых служб**" выберите **вкладку "Назначения** " и нажмите кнопку **"Добавить"**.
4. Следуйте указаниям мастера, чтобы назначить назначение, и выберите пользователей, которые должны быть добавлены в него. Назначение будет применяться ко всем комнатам и группам помещений.
5. В конце мастера назначения выберите " **Добавить назначение"**.

Пользователи, которым назначена роль администратора управляемой службы, отвечают за повседневное управление и мониторинг Комнаты Teams Premium управляемого портала служб.

После назначения пользователям роли администратора управляемой службы перейдите к устройству регистрации [](enroll-a-device.md) Комнаты Teams, чтобы добавить устройство Комнаты Teams на портал управляемой службы.

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
