---
title: Настройка ESC для голосовой почты в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: Сводка. сведения о настройке ESC голосовой почты в Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server.
ms.openlocfilehash: c9a858ead9261944c162cb10fda63840f8de86d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233576"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Настройка ESC для голосовой почты в Skype для бизнеса

**Сводка:** В этой статье рассказывается о том, как настроить escape-последовательность голосовой почты в Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server.

Когда пользователь настраивает Одновременный звонок на мобильный телефон, вызывающий абонент обычно перенаправляется на личную голосовую почту пользователя, если мобильный телефон выключен, не работает от аккумулятора или выходит за пределы диапазона. С помощью Skype для бизнеса Server пользователи могут присоединиться к деловой почтовой почте для звонков, связанных с бизнес-связью. В частности, можно настроить таймер, и если звонок отвечает на голосовую почту перевозчика в течение определенного периода времени, Skype для бизнеса Server отключается от системы голосовой почты перевозчика (и личной голосовой почты пользователя), а пользователь остальные конечные точки в корпоративной системе продолжают звонить. Таким образом, вызывающий абонент автоматически перенаправляется на корпоративную голосовую почту пользователя.

Эта настройка выполняется с помощью командлета командной консоли Skype для бизнеса Server, **Set-ксвоицеполици**на уровне политики голосовой связи со следующими параметрами.

### <a name="to-configure-voice-mail-escape"></a>Настройка escape-последовательности голосовой почты

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Задайте следующие параметры для **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.

   - **PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимы значения из диапазона 0 – 8000 миллисекунд.

## <a name="example"></a>Пример

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>См. также

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

