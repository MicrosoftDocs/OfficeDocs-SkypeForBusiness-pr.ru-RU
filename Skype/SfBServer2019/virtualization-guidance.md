---
title: 'Поддержка виртуализации для Skype для бизнеса Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Сведения о поддержке виртуализации в Skype для бизнеса Server 2019.
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509036"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Поддержка виртуализации для Skype для бизнеса Server 2019

Skype для бизнеса Server 2019 поддерживается для виртуализации.

Хотя виртуализация поддерживается, следует помнить о некоторых ключевых моментах:

- Поддержив соотношение виртуальных ЦП к физическому ЦП 1:1.
- Не перемещайте гостевой сервер во время его работы.
- Перенос живой системы и переносимость виртуальной машины не поддерживаются.
- Отключать hyper-threading на всех ведущих.
- Не настраивайте динамическую память на серверах хост-серверов.
- Используйте фиксированные или сквозные диски, а не динамические диски.
- Допускается 6–10 процентов накладных расходов для гипервизоров, которые не требуются виртуальному гостю.

## <a name="supported-hypervisors"></a>Поддерживаемые гипервизоры

SfB Server 2019 поддерживается в Windows Server 2016 и Windows Server 2019.

Для сторонних гипервизоров требуется гипервизор, который прошел тестирование программы проверки виртуализации серверов (SVVP) для соответствующей ОС.

- См. [версии Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) в списке SVVP.
- См. [версии Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) в списке SVVP.

## <a name="stress-and-performance-tool"></a>Средство для работы с нагрузкой и производительностью

Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019. Skype для бизнеса Server 2019 Stress and Performance Tool поможет вам:

- Упрощение планирования оборудования для Skype для бизнеса Server 2019
- Предоставление дополнительных знаний и лучших методик настройки производительности
- Измерение производительности предполагаемых развертывание Skype для бизнеса Server 2019
 
Вы можете скачать средство [здесь.](https://www.microsoft.com/download/details.aspx?id=101447)
