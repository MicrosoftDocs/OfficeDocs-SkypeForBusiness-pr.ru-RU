---
title: Ограничьте пользователей, которые могут видеть при поиске в каталоге в Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Узнайте, как ограничить пользователей, которые могут видеть при поиске по каталогу в Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046431"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Ограничьте пользователей, которые могут видеть при поиске в каталоге в Teams

Microsoft Teams позволяет организациям предоставлять пользователям настраиваемые представления каталога. Эти представления могут быть полезны, если:

- В рамках клиента организации существует множество компаний, которые должны быть независимы друг от друга.
- Бизнес-политики требуют, чтобы определенные группы в организации не взаимодействовали друг с другом.
- В учебном заведении требуется ограничить возможности общения преподавателей с учащимися в чатах.

Существует два варианта ограничения того, кто может видеть пользователей при поиске в каталоге в Teams:

- [Информационные барьеры в Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Политики адресной книги в Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)

При использовании любого из этих вариантов необходимо включить поиск по имени в Teams администрирования.

Мы рекомендуем использовать информационные барьеры, если ваша организация соответствует необходимым [лицензиям и разрешениям](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions).

Включение поиска по имени

1. В Microsoft Teams администрирования **выберите Teams** >  **Teams параметры**.

1. В **разделе "Поиск по имени**" рядом с полем поиска в каталоге scope с помощью политики **адресной** книги Exchange включите этот **переключатель**.

> [!Note]
> Чтобы это изменение вступает в силу, может потребоваться несколько часов.
> 
> Включение поиска по имени скрывает поле "Команды  поиска" и список общедоступных команд в  разделе "Присоединение" или создание команды в Teams. Он также отключит присоединение к `/join` команде, введя в командной строке в верхней части Teams.
