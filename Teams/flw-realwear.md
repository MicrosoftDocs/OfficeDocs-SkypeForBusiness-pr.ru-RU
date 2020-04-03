---
title: Информация ITAdmin для клиента Microsoft Teams RealWear (предварительная версия)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: A, ITAdmin - прохождение клиента RealWear для Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d3ead9c85fc58fdc55cd321e55b0ff9ca76853
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102397"
---
# <a name="realwear-for-microsoft-teams"></a>RealWear для Microsoft Teams

> [!NOTE]
> Это функция предварительной версии или предыдущего выпуска.

В этой статье рассказывается о клиенте Microsoft Teams для носимых головных устройств RealWear. Работники FirstLine, использующие RealWear HMT-1 и HMT-1Z1, теперь могут сотрудничать с удаленным экспертом, используя видеосвязь в Teams. С помощью голосового интерфейса пользователя Teams для RealWear позволяют работникам на местах оставаться на 100% свободными от рук, сохраняя ситуационную осведомленность в шумной и опасной обстановке. Показывая то, что они видят в режиме реального времени, полевые работники могут ускорить решение проблем и снизить риск дорогостоящих простоев.

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a>Как развернуть Microsoft Teams для RealWear

Клиент Microsoft Teams для RealWear в настоящее время находится в открытом предварительном просмотре. Для участия в этом предварительном просмотре вам потребуется следующее:

Устройства RealWear обновлены до версии 10.5.0 или выше. Больше информации [здесь](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).

> [!IMPORTANT]
> Зарегистрируйтесь [здесь](https://www.realwear.com/solutions/microsoft-teams/#C1) для доступа в клиента Teams для RealWear в [RealWear Foresight](https://cloud.realwear.com/).

## <a name="required-licenses"></a>Требуемые лицензии

Лицензии Microsoft Teams являются частью подписок на Office 365. Никакого дополнительного лицензирования для использования Teams для RealWear не требуется. Для получения дополнительной информации о получении команд ознакомьтесь с разделом  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="managing-realwear-devices"></a>Управление устройствами RealWear

### <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

Устройствами RealWear можно управлять в режиме администратора устройств Android. Поддержка управления через Android Enterprise ограничена, так как устройства в настоящее время не имеют мобильных сервисов Google (GMS).

- Подробнее об управлении устройствами RealWear в Microsoft Endpoint Manager см. в разделе [Регистрация администраторов устройств Android в Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).

### <a name="third-party-enterprise-mobility-managers-emms"></a>Сторонние менеджеры по корпоративной мобильности (EMM)

Руководство по сторонним EMM см. В разделе [Поддерживаемые поставщики управления мобильностью предприятия](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).
