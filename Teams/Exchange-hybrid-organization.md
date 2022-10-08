---
title: Настройка гибридной организации Exchange
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как настроить гибридную организацию Exchange для использования с Microsoft Teams, чтобы обеспечить синхронизацию членства в группах.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480679"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Настройка гибридной организации для работы с Microsoft Teams

В общем случае настраивать какие-либо функции Exchange Online для работы с Microsoft Teams не требуется. Однако в гибридной среде Exchange нужно принять определенные меры, чтобы синхронизировать членства в группах между Exchange Server (в локальной среде) и Exchange Online. Это включает включение функции обратной записи групп в Azure AD Connect, а также различные скрипты инициализации: Группы Microsoft 365 с локальным гибридным [приложением Exchange](/exchange/hybrid-deployment/set-up-microsoft-365-groups).