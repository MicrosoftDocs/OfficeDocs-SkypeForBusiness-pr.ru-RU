---
title: Объединение с устаревшей версией
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Внешний FQDN веб-конференций позволяет внешним пользователям присоединяться к локальному собранию. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.
ms.openlocfilehash: 9e24e3f89d3ed7e63406b0a7eb3e46201ae7e530
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836741"
---
# <a name="legacy-merge"></a>Объединение с устаревшей версией

Внешний **FQDN** веб-конференций позволяет внешним пользователям присоединяться к локальному собранию. Введите полное доменное имя (FQDN) внешнего интерфейса веб-конференции устаревшего edge Server.

Внешний **порт** внешнего порта веб-конференции **443** — это порт протокола инициации сеанса протокола управления передачей по умолчанию (TCP), настроенный для клиентов-конференциаторов. Если значение по умолчанию не использовалось, обнови внешнее значение **порта Внешние** веб-конференциалы.

Выберите пул **This Edge, используемый для** проверки подключений федерации и общего чата, если вы планируете использовать этот edge Server для федерации. Если развернуто несколько пограничных серверов, то для федерации будет включен только один из них. Если вы не проверяете это поле и решите позже включить федерацию, необходимо снова запустить мастер слияния строителей топологии, а также опубликовать топологию. Подробные сведения [см. в материале Phase 4: Merge Topologies.](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)