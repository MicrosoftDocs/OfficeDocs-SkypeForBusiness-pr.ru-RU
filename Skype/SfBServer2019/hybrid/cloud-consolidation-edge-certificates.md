---
title: Обновление сертификатов пограничного сервера
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
description: В этом приложении включает в себя подробные шаги для обновления сертификатов пограничного сервера как часть облака консолидации для групп и Скайп для бизнеса.
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247704"
---
# <a name="update-the-edge-certificate"></a>Обновление сертификатов пограничного сервера

Обновление сертификатов пограничного сервера — это ключевые шаг, чтобы проверка того, что на prem среде с SipDomain1 присоединиться к облачной среде с SipDomain2 и обеспечить правильную маршрутизацию в среде общее адресное пространство между этими двумя доменами SIP. В разделе шаг 14 в [облаке консолидации для групп и Скайп для бизнеса](cloud-consolidation.md) для контекста, в котором может выполнить это действие. В нашем примере SipDomain1 — AcquiredCompany. <span>com и SipDomain2 — это OriginalCompany. <span>com.

Альтернативное имя субъекта (SAN) сертификата на все пограничные серверы в локальной среде необходимо обновить для включения всех доменов SIP, существующих в чисто интерактивного клиента (за исключением любой onmicrosoft.<span> домены COM), в форме «sip. \<домена >».  В нашем примере это sip. OriginalCompany. <span>com. Этот шаг крайне важна для выполнения до миграции пользователей в облаке.

**Действия:**

1.  Получить новый сертификат для внешнего пограничного сервера для пограничного сервера, который содержит все существующие записи, а также дополнительные записи в сети хранения данных для всех доменов SIP в облачной среде (за исключением *. onmicrosoft.com домены) в виде «sip. <DomainName>«.
2.  Установите сертификат локально на каждом пограничном сервере и назначьте его Скайп Пограничная служба на каждом из службы пограничного сервера.  Подробное описание шагов в разделе «Внешний пограничный сервер интерфейса сертификаты» в [Развертывание службы пограничного сервера в Скайп для Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Перезапуск службы пограничного сервера на каждом пограничном сервере. Это можно сделать для одного поля с помощью следующей команды PowerShell:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>См. также

[Консолидация облако для групп и Скайп для бизнеса](cloud-consolidation.md)