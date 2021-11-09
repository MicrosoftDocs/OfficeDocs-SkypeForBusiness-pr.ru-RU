---
title: 'Поддержка виртуализации Skype для бизнеса Server 2019 г. '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: Сводка. Сведения о поддержке виртуализации Skype для бизнеса Server 2019 г.
ms.openlocfilehash: 73e9121e2b530e44395aefda50082682fb910e7d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853783"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Поддержка виртуализации Skype для бизнеса Server 2019 г.

Skype для бизнеса Server 2019 г. поддерживается виртуализация.

Хотя виртуализация поддерживается, необходимо помнить несколько ключевых моментов:

- Сохраните отношение виртуального ЦП к физическому процессору 1:1.
- Не перемещайте гостевой сервер во время его работы.
- Перенос живой системы и переносимости виртуальной машины не поддерживаются.
- Отключение гиперпотока для всех хостов.
- Не настраивайте динамическую память на хост-серверах.
- Используйте фиксированные или проходные диски, а не динамические диски.
- Разрешить для гипервизоров 6-10 процентов сверх того, что требуется виртуальному гостю.

## <a name="supported-hypervisors"></a>Поддерживаемые гипервизоры

SfB Server 2019 поддерживается на Windows Server 2016 и Windows Server 2019.

Для сторонних гипервизоров необходим гипервизор, который прошел тестирование программы проверки виртуализации сервера (SVVP) для соответствующей ОС.

- См. [Windows Server 2016 версии](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) в списке SVVP.
- В [списке SVVP Windows Server 2019.](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)

## <a name="stress-and-performance-tool"></a>Средство стресса и производительности

Средство Skype для бизнеса Server и производительности 2019 г. включает средства, упрощающий планирование емкости Skype для бизнеса Server 2019 г. Средство Skype для бизнеса Server 2019 года поможет вам:

- Упрощение планирования оборудования Skype для бизнеса Server 2019 г.
- Предоставление дополнительных знаний и практических методов для настройки производительности
- Измерение производительности ваших Skype для бизнеса Server 2019 г.
 
Вы можете скачать средство [отсюда](https://www.microsoft.com/download/details.aspx?id=101447).
