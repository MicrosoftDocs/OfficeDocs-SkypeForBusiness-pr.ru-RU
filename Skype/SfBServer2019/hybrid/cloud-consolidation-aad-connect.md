---
title: Обновление AAD подключения для включения более одного леса
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержит подробное описание действий по обновлению AAD подключиться к включению более одного леса в качестве части консолидации облако для групп и Скайп для бизнеса.
ms.openlocfilehash: d7229d54c159f7e07a233636f1576830e667dce5
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247713"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>Обновление AAD подключения для включения более одного леса

Подключение Azure AD поддерживает [синхронизацию из нескольких лесов](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies). Тем не менее он поддерживает только один экземпляр синхронизации Azure AD подключиться к AAD. Таким образом, в тех случаях, уже установленной Azure AD в одном лесу, необходимо обновить существующий экземпляр AAD подключения для синхронизации из дополнительных леса.

 - Если все удостоверения, представленные только один раз в обоих лесах (то есть, не было выполнено все контакты с включенной поддержкой почты), а затем просто повторно запустить мастер AAD подключения, нажмите кнопку «Настройка параметров синхронизации» и подключите свои каталоги на ** **введите имя дополнительного леса и учетных данных.<br><br>
 ![Подключение страницы каталоги](../media/cloud-consolidation-connect-your-directories.png)
 - Тем не менее если пользователи могут существовать в более чем одного каталога и вы будете объединения данных (например, если существуют объекты контактов в соответствии с пользователями в другом лесу лес), необходимо будет удалить подключение Azure AD и повторно установить его.  Это условие правила соединения между лесами можно настроить только во время первой установки. Для этого на следующей странице:<br><br>
 ![Однозначно идентифицирующая страницы пользователей](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>См. также

[Консолидация облако для групп и Скайп для бизнеса](cloud-consolidation.md)