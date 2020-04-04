---
title: Информация ИТ-администратора для клиента Microsoft Teams RealWear (предварительная версия)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Инструкции ИТ-администратора клиента Microsoft Teams для RealWear.
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
ms.openlocfilehash: e95440652111dbcd39b756ef942e7a974ef31de0
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131207"
---
# <a name="microsoft-teams-for-realwear"></a>Microsoft Teams для RealWear

> [!NOTE]
> Это функция для предварительного или раннего доступа.

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
- Подробнее о политиках см. в статье [Как использовать Intune в среде без мобильных служб Google](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).

### <a name="third-party-enterprise-mobility-managers-emms"></a>Сторонние менеджеры по корпоративной мобильности (EMM)

Руководство по сторонним EMM см. в статье [Поддерживаемые поставщики корпоративных служб управления мобильностью](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).

## <a name="end-user-content"></a>Содержимое для пользователей

Дополнительные сведения для конечных пользователей см. в статье [Использование Microsoft Teams для RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).
