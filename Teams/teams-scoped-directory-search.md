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
ms.openlocfilehash: 8b073cdd67d89de7d934990abc33cb0586d0fc76
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732227"
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
