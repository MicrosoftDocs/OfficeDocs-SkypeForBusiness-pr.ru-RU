---
title: Планирование удаленного управления звонками в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: В предыдущих версиях Lync Server функция удаленного управления звонками позволяла пользователям управлять телефонами УАЦ с помощью Lync Server. В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы". In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813519"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Планирование удаленного управления звонками в Skype для бизнеса
 
В предыдущих версиях Lync Server функция удаленного управления звонками позволяла пользователям управлять телефонами УАЦ с помощью Lync Server. В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы".  *In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.* 
  
 Пользователи удаленного управления звонками в организации, которые находятся на серверах переднего сервера с Lync Server, могут продолжать использовать удаленное управление звонками, даже если они используют клиент Skype для бизнеса. Однако для всех пользователей, которые были в Skype для бизнеса Server, удаленное управление звонками не поддерживается. См. следующую таблицу для комбинаций серверов и клиентов, а также о том, могут ли они поддерживать удаленное управление вызовами или вызов с помощью работы.
  
||**Клиент Skype для бизнеса с включенным пользовательским интерфейсом Skype**|**Клиент Skype для бизнеса с включенным пользовательским интерфейсом Lync**|**Клиент Skype для бизнеса 2016**|**Клиент Lync 2013**|**Клиент Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype для бизнеса Server <br/> |Вызов с рабочего телефона  <br/> |1  <br/> |Вызов с рабочего телефона  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |1  <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |
| Lync Server 2010 <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |1  <br/> |Удаленное управление звонками  <br/> |Удаленное управление звонками  <br/> |
   
1. Ни одна из функций не поддерживается.
  
Дополнительные сведения [см.](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по удаленному контролю вызовов в Lync Server 2013.
  
## <a name="see-also"></a>См. также

[Планирование звонков с помощью работы в Skype для бизнеса Server](call-via-work.md)
  
[Сравнение функций классических клиентов в Skype для бизнеса](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Позвонить в Skype для бизнеса, но использовать настольный телефон УАКСИ для аудиосвязи](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

