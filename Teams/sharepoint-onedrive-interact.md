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
ms.openlocfilehash: 99667735c6e0e71532084f3aff6771df4408f892
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646210"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Взаимодействие SharePoint OneDrive взаимодействия с Microsoft Teams

> [!Tip]
> В следующем сеансе вы узнаете Teams как Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint и OneDrive: основы [Microsoft Teams](https://aka.ms/teams-foundations)

У каждой группы Microsoft Teams есть сайт группы в SharePoint, а каждый стандартный канал группы получает папку в библиотеке документов сайта группы по умолчанию. Каждый [частный канал](private-channels.md) имеет собственный отдельный SharePoint сайт. Дополнительные информацию об этих сайтах группы и каналах см. в Teams [подключенных сайтов и сайтов каналов.](/sharepoint/teams-connected-sites)

Файлы, совместно используемые во время беседы, автоматически добавляются в библиотеку документов, а заданные в SharePoint разрешения и параметры безопасности файлов автоматически переносятся в Teams. Чтобы узнать, как изменение адреса сайта влияет на SharePoint, см. статью Изменение [адреса сайта.](/sharepoint/change-site-address)

Личные файлы чата хранятся в папке отправитель OneDrive, и разрешения автоматически предоставлены всем участникам в процессе предоставления общего доступа к файлам.

Если пользователям не назначены SharePoint лицензии, у них нет OneDrive хранилища в Microsoft 365. Общий доступ к файлам работает в стандартных каналах, но пользователи не смогут делиться файлами в чатах без OneDrive хранения в Microsoft 365.

При хранении файлов в SharePoint документа и OneDrive правила соответствия требованиям, настроенные на уровне организации, будут следовать. 

> [!NOTE]
> Интеграция с SharePoint Server не поддерживается для Teams.

Ниже приводится пример связей между командой, стандартным каналом и библиотекой документов.

Для каждой команды создается сайт SharePoint, а также папка по умолчанию **Общие документы**. У каждого стандартного канала, включая канал **"Общее"** (канал по умолчанию для каждой команды), есть папка в **общих документах.**

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
- Сразу же проверяет, является ли файл файлом только для чтения или иным.
- И ознакомьтесь с файлами.
- Закрепить, открепить и изменить порядок сортировки файлов.
- Определение файлов, которым нужны метаданные
- Выберите один из множества других параметров фильтрации.
- Группируются файлы на основе заголовков столбцов.
- Изменение параметров столбца (перемещение влево или вправо, скрытие) и ширины столбцов.

## <a name="default-link-type-setting"></a>Тип ссылки по умолчанию

Тип ссылки общего доступа, который отображается по умолчанию, если пользователь поделился файлом в центре SharePoint администрирования. Сведения см. в разделе Изменение типа ссылки по умолчанию [при ссылке для общего доступа.](/sharepoint/change-default-sharing-link)

## <a name="related-topics"></a>Статьи по теме

[SharePoint и Teams: лучше вместе](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

[Взаимодействие с гостями](guest-experience.md)