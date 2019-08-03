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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные инструкции по обновлению AAD Connect для включения нескольких лесов в состав облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160713"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Обновление AAD Connect для включения нескольких лесов

Azure AD Connect поддерживает [синхронизацию из нескольких лесов](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Однако он поддерживает только один экземпляр Azure AD Connect Sync to AAD. Таким образом, если служба Azure AD уже установлена в одном лесу, существующий экземпляр AAD Connect необходимо обновить для синхронизации с дополнительным лесом.

 - Если все удостоверения представлены только один раз в обоих лесах (то есть контакты с включенной поддержкой почты не были настроены), можно просто повторно запустить мастер подключения AAD, выбрать пункт "Настройка параметров синхронизации", а затем на странице **подключить каталоги. **введите имя дополнительного леса и учетных данными.<br><br>
 ![Страница подключения каталогов](../media/cloud-consolidation-connect-your-directories.png)
 - Тем не менее, если пользователи могут находиться в нескольких каталогах и вы будете объединять данные (например, если объекты Contact существуют в лесу, соответствующем пользователям в другом лесу), необходимо удалить Azure AD Connect и повторно установить ее.  Это связано с тем, что условие правил подключения между лесами можно настроить только при первой установке. Это делается на следующей странице:<br><br>
 ![Страница уникальной идентификации пользователей](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>См. также

[Объединение в облако для Teams и Skype для бизнеса](cloud-consolidation.md)