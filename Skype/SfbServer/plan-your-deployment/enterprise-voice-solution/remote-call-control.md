---
title: Планирование удаленного управления звонками в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Удаленное управление звонками — это функция в предыдущих версиях Lync Server, на которой пользователи смогут управлять телефонным АТС с помощью Lync Server. В Skype для бизнеса Server эта функция заменена на "звонок через Work". В клиентских версиях Skype для бизнеса Server 2015 и переходе к следующему элементу управления удаленным звонком больше нельзя настроить в клиенте и он был удален для использования.
ms.openlocfilehash: e98bcbd7e1feb91b31994d2ece2770c911547882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276492"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Планирование удаленного управления звонками в Skype для бизнеса
 
Удаленное управление звонками — это функция в предыдущих версиях Lync Server, на которой пользователи смогут управлять телефонным АТС с помощью Lync Server. В Skype для бизнеса Server эта функция заменена на "звонок через Work".  *В клиентских версиях Skype для бизнеса Server 2015 и переходе к следующему элементу управления удаленным звонком больше нельзя настроить в клиенте и он был удален для использования.* 
  
 Пользователи удаленного управления звонками в вашей организации, которые размещаются на серверах переднего плана с Lync Server, могут продолжать использовать удаленное управление звонками даже в том случае, если они используют клиента Skype для бизнеса. Тем не менее, для всех пользователей, которые подключены к Skype для бизнеса Server, не поддерживается управление удаленными звонками. See the following table for server/client combinations and whether they can support remote call control or Call via Work.
  
||**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Skype**|**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Lync**|**Клиент Skype для бизнеса 2016**|**Клиент Lync 2013**|**Клиент Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype для бизнеса Server <br/> |Вызов с рабочего телефона  <br/> |1 <br/> |Вызов с рабочего телефона  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |1,1 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |
| Lync Server 2010 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |1,1 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |
   
1. Ни одна из функций не поддерживается.
  
Дополнительные сведения можно найти в разделе [Управление удаленными звонками](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по Lync Server 2013.
  
## <a name="see-also"></a>См. также

[Планирование звонков с помощью Skype для бизнеса Server](call-via-work.md)
  
[Сравнение возможностей настольного клиента в Skype для бизнеса](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Совершение звонков в Skype для бизнеса с помощью телефона в стационарном устройстве УАТС для звука](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

