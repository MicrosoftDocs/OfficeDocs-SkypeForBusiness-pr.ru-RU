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
localization_priority: Normal
description: В этом приложении содержатся подробные инструкции по обновлению пограничного сертификата в составе облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888608"
---
# <a name="update-the-edge-certificate"></a>Обновление пограничного сертификата

Обновление пограничного сертификата это ключевой этап, позволяющий убедиться, что локальная среда с SipDomain1 может присоединиться к облачной среде с SipDomain2 и обеспечить правильную маршрутизацию в среде общего адресного пространства для двух доменов SIP. На этапе 14 в разделе [Консолидация в облаке для Teams и Skype для бизнеса](cloud-consolidation.md) в контексте, в котором вы можете выполнить этот шаг. В нашем примере SipDomain1 — Аккуиредкомпани. <span>com и SipDomain2 — оригиналкомпани. <span>com.

Необходимо обновить альтернативное имя субъекта (SAN) сертификата на всех пограничных серверах в локальной среде, чтобы включить все домены SIP, существующие в чистом сетевом клиенте (за исключением всех протоколов onmicrosoft.<span> домены com) в виде "SIP. \<> домена ".  В нашем примере это SIP. Оригиналкомпани. <span>com. Этот шаг очень важен перед переносом пользователей в облако.

**Образом**

1.  Получите новый внешний пограничный сертификат для пограничного сервера, у которого есть все существующие записи и дополнительные записи в сети SAN для всех доменов SIP в облачной среде (кроме доменов *. onmicrosoft.com) в форме "SIP. <DomainName>".
2.  Установите сертификат локально на каждом пограничном сервере и назначьте его службе пограничной службы Skype для каждой пограничной службы.  Подробное описание действий приведено в разделе "сертификаты внешнего интерфейса [пограничной службы" в службе развертывания пограничной службы в Skype для бизнеса Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Перезапустите пограничную службу на всех пограничных серверах. Это можно сделать для одного поля с помощью следующих команд PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>См. также

[Объединение в облако для Teams и Skype для бизнеса](cloud-consolidation.md)