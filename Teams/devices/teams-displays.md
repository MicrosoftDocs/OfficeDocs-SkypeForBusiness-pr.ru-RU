---
title: Microsoft Teams отображает
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: В этой статье дается обзор функций, поддерживаемых Microsoft Teams дисплеев.
ms.openlocfilehash: 77af5392b539045cdbacda2d6c278d35098437ed
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514682"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams отображает

Microsoft Teams дисплеи — это категория полностью выделенных устройств Teams, которые имеют сенсорный экран с сенсорным экраном с сенсорным экраном и без рук на Кортана. В этой статье представлен обзор Teams, которые помогут вам планировать, предоставлять и управлять Teams экранами в организации.

Teams на&ndash; одном устройстве отображаются Teams функции чата, собраний, звонков,&ndash; календаря и файлов. Благодаря Teams экрана пользователи могут использовать микрофон, камеру и динамики (или Bluetooth гарнитуру) для надежных звонков и собраний. Teams интегрируется с компьютерами Windows пользователей, чтобы обеспечить взаимодействие между устройствами.

Дополнительные информацию можно найти в [этой Teams экранах](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Функции, поддерживаемые Teams дисплеях

Помимо функций[, поддерживаемых Teams телефонов](phones-for-teams.md#features-supported-by-teams-phones), следующие функции уникальны для Teams дисплеев:

- **Специальные дисплеи для** Teams. Пользователи могут получать доступ ко всем основным функциям Teams, включая чат, собрания, звонки, команды и каналы, файлы и т. д.
- **Окружающее время** Пользователи могут без контекстного переключателя видеть важные действия и уведомления, не переключаясь между основными устройствами. Пользователи также могут персонализировать Teams, настроив фон с помощью параметров.
-  Без помощи рук Кортана Пользователи могут взаимодействовать с Teams, используя свой голос, чтобы легко присоединяться к собраниям и участвовать в них, диктовать ответы в чате Teams, проверять, что в календаре, и делать много другое.
- **Оставьте заметку на экране блокировки** Гости могут оставить звуковые, видео- и текстовые заметки, а пользователи смогут проверять заметки, оставленные гостями, и видеть, кто их останавливает.  

## <a name="required-licenses"></a>Необходимые лицензии

Teams лицензии можно приобрести в рамках Microsoft 365 [и Office 365 подписки](/office365/servicedescriptions/teams-service-description). Дополнительные информацию о необходимых лицензиях для использования дисплеев Teams см. в этой [Microsoft Teams.](https://products.office.com/microsoft-teams/voice-calling)

Дополнительные сведения о том, как Teams, можно найти в этой Microsoft Teams[.](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Развертывание Teams с помощью Intune

Дополнительные информацию о развертывании Teams с помощью Intune см. в Teams и Teams [телефонов](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Управление Teams дисплеями в организации

Чтобы управлять устройствами Teams экрана, в левой области навигации центра администрирования Microsoft Teams перейдите к Teams **экранам**. Здесь вы можете изменить профиль конфигурации устройства, управлять обновлениями, перезапустить устройства, добавить и удалить теги устройств и другие. Дополнительные сведения см. в [Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Настройка службы поддержки на Teams экранах

С помощью службы hot desking люди в вашей организации могут заранее резервировать временные Teams и Outlook или с самого устройства. Если включена возможность службы hot desking, пользователи могут войти в Teams, Microsoft 365 свои учетные данные для доступа к собраниям, чатам и файлам. При выходе все личные сведения удаляются с устройства.

Для начала необходимо приобрести лицензии Комнаты Microsoft Teams стандартный и создать учетные записи ресурсов для каждого Teams экрана. См[. раздел Создание учетных записей ресурсов](../rooms/with-office-365.md) для помещений и общих Teams устройств для создания учетных записей ресурсов.

После создания учетных записей ресурсов вы можете создать и назначить политику, чтобы включить службу поддержки. [Дополнительные узнать см. в новой CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps).

> [!IMPORTANT]
> Так как Teams с помощью службы hot desking используются в общих рабочих пространствах несколькими людьми, правила условного доступа и другие конфигурации удостоверений в вашей среде, например многофакторная проверка подлинности, могут повлиять на эти устройства и вызвать проблемы со входом. Рекомендации по защите общих устройств см. в руководстве по проверке подлинности общих Teams [устройствах с Android](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Обновление Teams телефонов до Teams дисплеев

Teams дисплеев — это развитие Teams телефонов. Вы можете обновить Teams телефонов в организации, чтобы Teams отображались с помощью Microsoft Teams центра администрирования. Этот параметр доступен только для телефонов, поддерживаюющих обновление до Teams дисплеев. Дополнительные информации см. в [Teams телефонах до Teams дисплеев](upgrade-phones-to-displays.md).

## <a name="see-also"></a>См. также

[Знакомство с Microsoft Teams экрана](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Телефоны для Teams](phones-for-teams.md)

[IP-телефоны, сертифицированные для Microsoft Teams](teams-ip-phones.md)

[Обновление IP-телефонов до Teams дисплеев](upgrade-phones-to-displays.md)

[Кортана голосовой помощи в Teams](../cortana-in-teams.md)