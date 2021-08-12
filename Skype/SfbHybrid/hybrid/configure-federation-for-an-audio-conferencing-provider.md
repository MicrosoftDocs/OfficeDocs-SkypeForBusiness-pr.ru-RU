---
title: Настройка федерации для поставщика аудиоконференций в гибридном развертывании
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Сводка. Сведения о настройке федерации для поставщика аудиоконференций в Skype для бизнеса Online.
ms.openlocfilehash: 3e01615c65777508c2adead26dd15ca85afbb102e04d8ba57492826942f86672
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301825"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Настройка федерации для поставщика аудиоконференций в гибридном развертывании

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Сводка:** Узнайте, как настроить федерацию для поставщика аудиоконференций в Skype для бизнеса Online.

Если вы хотите использовать поставщика аудиоконференций (ACP) в гибридном развертывании (локально с помощью сети), необходимо настроить федерацию между локальной развертыванием и партнером ACP в качестве разрешенного сервера-партнера. Вы можете настроить федерацию, добавив домен партнера ACP и сервер Edge (это также можно назвать прокси-сервер доступа) в список федератированных доменов для локального развертывания. Затем партнеру ACP необходимо добавить FQDN локального пула Edge Server в разрешенный список федераированных доменов. Дополнительные сведения обратитесь к поставщику ACP. Затем партнеру ACP необходимо добавить FQDN локального пула Edge Server в разрешенный список федераированных доменов.

- **Добавление домена ACP и edge Server в качестве разрешенного федератного домена**

    Чтобы добавить домен ACP в качестве разрешенного сервера партнеров (разрешенный федераированный домен), выполните действия в Настройка поддержки разрешенных [внешних доменов.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains) Для edge Server добавьте FQDN edge Server партнера ACP. Возможно, вам потребуется связаться со своим партнером по ACP, чтобы получить FQDN для их edge Server, который также может быть передан вашей ACP в качестве их прокси-доступа.

- **Предоставление FQDN вашего пула edge Server партнеру ACP**

    Партнеру ACP необходимо настроить федерацию для добавления локального домена в качестве разрешенного сервера-партнера, добавив FQDN вашего пула edge Server в разрешенный федерательный домен.