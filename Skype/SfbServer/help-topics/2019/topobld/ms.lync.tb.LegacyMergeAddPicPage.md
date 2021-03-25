---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Внешний FQDN веб-конференций позволяет внешним пользователям присоединяться к локальному собранию. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.
ms.openlocfilehash: 87b70bc6d577f2752c00c7f7f73577eac7e759fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121070"
---
# <a name="legacy-merge"></a>Объединение с устаревшей версией

Внешний **FQDN** веб-конференций позволяет внешним пользователям присоединяться к локальному собранию. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.

Внешний **порт** внешнего порта веб-конференции **443** — это порт протокола инициации сеанса протокола управления передачей по умолчанию (TCP), настроенный для клиентов-конференциаторов. Если значение по умолчанию не использовалось, обнови внешнее значение **порта Внешние** веб-конференциалы.

Выберите пул **This Edge, используемый для** проверки подключений федерации и общего чата, если вы планируете использовать этот edge Server для федерации. Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них. Если вы не проверяете это поле и решите позже включить федерацию, необходимо снова запустить мастер слияния строителей топологии, а также опубликовать топологию. Подробные сведения [см. в материале Phase 4: Merge Topologies.](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)