---
title: 'Поддержка виртуализации Skype для бизнеса Server 2019 '
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
description: Сводка. сведения о поддержке виртуализации в Skype для бизнеса Server 2019.
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509036"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Поддержка виртуализации Skype для бизнеса Server 2019

Skype для бизнеса Server 2019 поддерживается в виртуализации.

Хотя виртуализация поддерживается, есть некоторые ключевые моменты, которые следует запомнить:

- Поддерживать 1:1 отношение виртуального ЦП к физическому ЦП.
- Не перемещайте гостевой сервер во время его работы.
- Миграция действующей системы и переносимость виртуальной машины не поддерживаются.
- Отключение технологии Hyper – Threading на всех узлах.
- Не настраивайте динамическую память на серверах узлов.
- Используйте фиксированные или транзитные диски, а не динамические диски.
- Разрешите 6-10 процентов для низкоуровневых оболочек, не превышающих требования к виртуальной машине.

## <a name="supported-hypervisors"></a>Поддерживаемые низкоуровневые оболочки

SfB Server 2019 поддерживается в Windows Server 2016 и Windows Server 2019.

Для низкоуровневых оболочек необходимы Гипервизоры, которые прошли тестирование программы проверки виртуализации серверов (SVVP) для соответствующей ОС.

- Ознакомьтесь с [версиями Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) , приведенными в списке SVVP.
- Ознакомьтесь с [версиями Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) , приведенными в списке SVVP.

## <a name="stress-and-performance-tool"></a>Средство нагрузки и производительности

Средство "нагрузочное тестирование и производительность" Skype для бизнеса Server 2019 включает средства, упрощающие планирование емкости для Skype для бизнеса Server 2019. Средство "нагрузочное тестирование и производительность" Skype для бизнеса Server 2019 поможет вам:

- Упростите планирование оборудования для Skype для бизнеса Server 2019
- Расширенные знания и рекомендации по настройке производительности
- Измерение производительности предполагаемых развертываний Skype для бизнеса Server 2019
 
Вы можете скачать средство отсюда [отсюда](https://www.microsoft.com/download/details.aspx?id=101447).
