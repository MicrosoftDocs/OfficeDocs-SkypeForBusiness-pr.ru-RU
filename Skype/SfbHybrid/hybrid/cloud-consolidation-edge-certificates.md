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
description: В этом приложении содержатся подробные инструкции по обновлению сертификата edge в рамках консолидации облака для Teams и Skype для бизнеса.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888608"
---
# <a name="update-the-edge-certificate"></a>Обновление пограничного сертификата

Обновление сертификата границы — это ключевой шаг, обеспечивающий, чтобы среда с SipDomain1 в среде, в которой есть SipDomain1, присоединила облачную среду с SipDomain2 и обеспечивала правильную маршрутизацию в общей среде адресного пространства между двумя доменами SIP. См. шаг 14 в консолидации [облачных звонков](cloud-consolidation.md) для Teams и Skype для бизнеса для контекста, в котором можно выполнить это шаг. В наших примерах SipDomain1 — AcquiredCompany. <span> com и SipDomain2 — OriginalCompany. <span> com.

Альтернативное имя субъекта (SAN) сертификата на всех серверах в локальной среде необходимо обновить, чтобы включить все домены SIP, которые существуют в чисто интерактивном клиенте (за исключением любых onmicrosoft). <span> com domains), в формате "sip. \< домен>".  В нашем примере это sip. OriginalCompany. <span> com. Это крайне важно сделать перед переносом пользователей в облако.

**Шаги:**

1.  Получите новый сертификат внешней границы для края, который имеет все существующие записи, а также дополнительные записи в SAN для всех доменов SIP в облачной среде (за исключением доменов *.onmicrosoft.com) в формате <DomainName> "sip.".
2.  Установите сертификат локально на каждом сервере и назначьте его службе Skype Edge на каждой из этих служб.  Дополнительные сведения см. в разделе "Сертификаты внешнего интерфейса внешнего интерфейса" статьи "Развертывание службы [edge в Skype для бизнеса Server 2015".](https://technet.microsoft.com/library/dn951368.aspx)
3.  Перезапустите по краям службу на каждом из этих серверов. Это можно сделать для одного окна с помощью следующих команд PowerShell:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>См. также

[Консолидация облака для Teams и Skype для бизнеса](cloud-consolidation.md)