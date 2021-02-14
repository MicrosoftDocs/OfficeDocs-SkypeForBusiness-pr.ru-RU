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
description: В этом приложении содержатся подробные инструкции по обновлению AAD Connect, чтобы включить несколько лесов в рамках консолидации облака для Teams и Skype для бизнеса.
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049101"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Обновление AAD Connect для включения нескольких лесов

Azure AD Connect поддерживает [синхронизацию из нескольких лесов.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies) Однако он поддерживает только один экземпляр синхронизации Azure AD Connect с AAD. Поэтому в случаях, когда Azure AD уже установлен в одном лесу, существующий экземпляр AAD Connect необходимо обновить для синхронизации из дополнительного леса.

 - Если все удостоверения представлены только один раз в обоих лесах (то есть вы не сделали контактов с включенной поддержкой почты), можно просто повторно запустить  мастер AAD Connect, выбрать "Настройка параметров синхронизации", а затем на странице "Подключение каталогов" введите имя дополнительного леса и creds.<br><br>
 ![Страница "Подключение каталогов"](../media/cloud-consolidation-connect-your-directories.png)
 - Однако если пользователи могут существовать в более чем одном каталоге и вы будете совмещать данные (например, если контактные объекты существуют в лесу, соответствующем пользователям в другом лесу), вам потребуется удалить Azure AD Connect и повторно установить его.  Это обусловлено тем, что условие правил join между лесами можно настроить только во время первой установки. Это делается на следующей странице:<br><br>
 ![Страница уникальной идентификации пользователей](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>См. также

[Консолидация облака для Teams и Skype для бизнеса](cloud-consolidation.md)