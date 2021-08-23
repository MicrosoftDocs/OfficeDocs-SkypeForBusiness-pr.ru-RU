---
title: Взаимодействие SharePoint OneDrive взаимодействия с Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive взаимодействия с Teams; личные хранилища файлов чата & взаимодействия между командой, стандартным каналом и & библиотекой документов.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b47ca7c1c0a9a5154f681a8e09d175ba17ad8013
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359196"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Взаимодействие SharePoint OneDrive взаимодействия с Microsoft Teams

> [!Tip]
> В следующем сеансе вы узнаете, Teams взаимодействия с Azure Active Directory(AAD), группами Microsoft 365, Exchange, SharePoint и OneDrive: основы [Microsoft Teams](https://aka.ms/teams-foundations)

У каждой Microsoft Teams есть сайт группы в SharePoint, а каждый стандартный канал группы получает папку в стандартной библиотеке документов сайта группы. Каждый [частный](private-channels.md) канал имеет собственный отдельный SharePoint сайт. Дополнительные информацию об этих сайтах группы и каналах см. в Teams [подключенных сайтов и сайтов каналов.](/sharepoint/teams-connected-sites)

Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams. Чтобы узнать, как изменение адреса сайта повлияет на SharePoint, см. статью Изменение [адреса сайта.](/sharepoint/change-site-address)

Личные файлы чата хранятся в папке OneDrive отправитель, а разрешения автоматически предоставлены всем участникам в процессе предоставления общего доступа к файлам.

Если пользователям не назначены SharePoint лицензии, у них нет OneDrive в Microsoft 365. Общий доступ к файлам работает в стандартных каналах, но пользователи не смогут делиться файлами в чатах без OneDrive хранения в Microsoft 365.

При хранении файлов в SharePoint и OneDrive правила соответствия требованиям, настроенные на уровне организации, будут следовать. 

> [!NOTE]
> Интеграция с SharePoint Server не поддерживается Teams.

Ниже приводится пример связей между командой, стандартным каналом и библиотекой документов.

Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**. У каждого стандартного канала, включая канал **Общий** (канал по умолчанию для каждой команды), есть папка в **общие документы.**

![Схема папок "Общие документы" в SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Стандартные SharePoint сайта и библиотеки документов нельзя заменить другими.

У каждого пользователя имеется папка OneDrive **Файлы чатов Microsoft Teams** для хранения всех файлов, предоставленных для общего доступа в приватных чатах с другими пользователями (в формате один к одному или один ко многим). При этом разрешения для ограничения доступа настраиваются автоматически.

![Схема папки OneDrive "Файлы чата Microsoft Teams чата"](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Обратите внимание, что для общедоступных SharePoint группы предусмотрен доступ "Все, кроме внешних пользователей". Команда не отображается в Teams для людей, которые не являются членами этой команды. Однако они могут получать доступ к контенту SharePoint сайта группы, используя URL-адрес SharePoint сайта группы. 

## <a name="channel-files-tab"></a>Вкладка "Файлы канала"

Вкладка **Файлы** в Teams напоминает представление SharePoint документов. На **вкладке** Файлы пользователи могут:

- Дополнительные параметры в **меню Новый** файл.
- Синхронизируйте файлы с локальным диском.
- В меню **Все документы переключение** из представления **"Список"** в представление **"Сжатое"** в представление **"Плитки".**
- Определите файлы, которые требуют внимания или имеют вредоносные программы.
- Сразу же поймем, является ли файл только для чтения или иным.
- И ознакомьтесь с файлами.
- Закрепить, открепить и изменить порядок сортировки файлов.
- Определение файлов, которым нужны метаданные
- Выберите один из множества других параметров фильтрации.
- Группировка файлов на основе заголовков столбцов.
- Изменение параметров столбца (перемещение влево или вправо, скрытие) и ширины столбцов.

## <a name="default-link-type-setting"></a>Тип ссылки по умолчанию

Тип ссылки общего доступа, который отображается по умолчанию, если пользователь поделился файлом в центре SharePoint администрирования. Сведения см. в разделе [Изменение типа ссылки по умолчанию, когда](/sharepoint/change-default-sharing-link) пользователи получают ссылки для общего доступа.

## <a name="related-topics"></a>Связанные статьи

[Управление Teams подключенными сайтами и сайтами каналов](/SharePoint/teams-connected-sites)

[SharePoint и Teams: лучше вместе](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

[Взаимодействие с гостями](guest-experience.md)
