---
title: Обновление AAD Connect для включения нескольких лесов
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные действия по обновлению AAD Connect, чтобы включить несколько лесов в рамках консолидации облаков для Teams и Skype для бизнеса.
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120378"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Обновление AAD Connect для включения нескольких лесов

Azure AD Connect поддерживает [синхронизацию из нескольких лесов.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Однако он поддерживает только один экземпляр синхронизации Azure AD Connect с AAD. Поэтому в случаях, когда Azure AD уже установлена в одном лесу, существующий экземпляр AAD Connect должен быть обновлен для синхронизации из дополнительного леса.

 - Если все удостоверения представлены только один раз в обоих лесах (то есть контакты с поддержкой почты не установлены), можно просто повторно запустить мастер AAD Connect, выбрать параметры синхронизации, а затем на странице **Connect Your Directories** введите имя дополнительного леса и creds.<br><br>
 ![Страница Подключение каталогов](../media/cloud-consolidation-connect-your-directories.png)
 - Однако, если пользователи могут существовать в более чем одном каталоге, и вы будете совмещать данные (например, если контактные объекты существуют в лесу, соответствующем пользователям в другом лесу), вам потребуется удалить Azure AD Connect и повторно установить его.  Это обусловлено тем, что условие правил межлесного присоединяться может быть настроено только во время первой установки. Это делается на следующей странице:<br><br>
 ![Страница Uniquely identifying your users](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>См. также

[Консолидация облаков для команд и Skype для бизнеса](cloud-consolidation.md)