---
title: Обновление пограничного сертификата
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
description: В этом приложении содержатся подробные действия по обновлению краевого сертификата в рамках консолидации облаков для Teams и Skype для бизнеса.
ms.openlocfilehash: bb8d2eabf17d83546737d3d94fb4add5dc0a892e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857116"
---
# <a name="update-the-edge-certificate"></a>Обновление пограничного сертификата

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Обновление краевого сертификата — это ключевой шаг к обеспечению того, чтобы предварительная среда с SipDomain1 присоединялась к облачной среде с SipDomain2 и обеспечивала надлежащую маршрутизацию в общей среде адресного пространства в двух доменах SIP. См. шаг 14 в консолид Teams и [Skype для бизнеса](cloud-consolidation.md) контексте, в котором можно выполнить этот шаг. В наших примерах SipDomain1 является AcquiredCompany. <span> com и SipDomain2 — это OriginalCompany. <span> com.

Альтернативное имя субъекта (SAN) сертификата на всех краевом сервере в локальной среде должно быть обновлено, чтобы включить все домены SIP, которые существуют в чистом онлайн-клиенте (за исключением любых onmicrosoft). <span> com доменов), в форме "sip. \<domain> ".  В нашем примере это глоток. OriginalCompany. <span> com. Этот шаг необходимо сделать перед переносом пользователей в облако.

**Действия:**

1.  Получение нового сертификата External Edge для края, который имеет все существующие записи, а также дополнительные записи в SAN для всех доменов SIP в облачной среде (за исключением доменов *.onmicrosoft.com) в форме `sip.<DomainName>` .
2.  Установите сертификат локально на каждом краевом сервере и назначьте его службе Skype edge на каждой из служб края.  Подробные действия см. в разделе "Внешние сертификаты интерфейса края" в службе развертывания edge [в Skype для бизнеса Server 2015 г.](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Перезапустите службу Edge на каждом из серверов края. Это можно сделать для одного окна со следующими командами PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>См. также

[Консолидация облаков для Teams и Skype для бизнеса](cloud-consolidation.md)