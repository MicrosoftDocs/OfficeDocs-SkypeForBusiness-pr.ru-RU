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
ms.localizationpriority: medium
description: В этом приложении содержатся подробные действия по обновлению Подключение AAD, чтобы включить несколько лесов в рамках консолидации облаков для Teams и Skype для бизнеса.
ms.openlocfilehash: e803ae1e41fd0e68a56e059bbaf398ee30f807f6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625801"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Обновление AAD Connect для включения нескольких лесов

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD Подключение поддерживает [синхронизацию из нескольких лесов.](/azure/active-directory/connect/active-directory-aadconnect-topologies) Однако он поддерживает только один экземпляр azure AD Подключение синхронизации с AAD. Поэтому в тех случаях, когда Azure AD уже установлена в одном лесу, существующий экземпляр AAD Подключение для синхронизации с дополнительным лесом.

 - Если все удостоверения представлены только один раз в обоих лесах (то есть контакты с поддержкой почты не установлены), можно просто повторно запустить мастер AAD Подключение, выбрать параметры синхронизации, а затем на странице **Подключение Каталоги** введите имя дополнительного леса и creds.<br><br>
 ![Страница Подключение каталогов](../media/cloud-consolidation-connect-your-directories.png)
 - Однако, если пользователи могут существовать в более чем одном каталоге, и вы будете сблигировать данные (например, если контактные объекты существуют в лесу, соответствующем пользователям в другом лесу), вам потребуется удалить Azure AD Подключение и повторно установить его.  Это обусловлено тем, что условие правил межлесного присоединяться может быть настроено только во время первой установки. Это делается на следующей странице:<br><br>
 ![Страница Uniquely identifying your users](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>См. также

[Консолидация облаков для Teams и Skype для бизнеса](cloud-consolidation.md)