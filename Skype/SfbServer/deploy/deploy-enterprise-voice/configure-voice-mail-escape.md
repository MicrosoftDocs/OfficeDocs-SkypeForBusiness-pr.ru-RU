---
title: Настройка escape-сообщения голосовой почты в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: Сводка. Узнайте, как настроить escape-вызов голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнеса Server.
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824929"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Настройка escape-сообщения голосовой почты в Skype для бизнеса

**Сводка:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.

Когда пользователь настраивает одновременные звонки на мобильный телефон, звонячий обычно перенанается на личную голосовую почту пользователя, если мобильный телефон отключен, выключен или находится вне диапазона. С помощью Skype для бизнеса Server пользователи могут выбрать перена маршрутизов, связанных с бизнесом, в корпоративную систему голосовой почты. В частности, можно настроить timer, и если на вызов отвечает голосовая почта оператора в течение определенного диапазона времени, Skype для бизнеса Server отключается от системы голосовой почты оператора (и личной голосовой почты пользователя), а остальные конечные точки пользователя в корпоративной системе продолжают звонить. Таким образом, вызываемая почта автоматически маршрутируется в корпоративную голосовую почту пользователя.

Эта конфигурация выполняется с помощью команды Skype для бизнеса Server Management Shell **Set-CsVoicePolicy** на уровне политики голосовой связи со следующими параметрами.

### <a name="to-configure-voice-mail-escape"></a>Настройка escape-сообщения голосовой почты

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Задайте следующие параметры для **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.

   - **PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.

## <a name="example"></a>Пример

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>См. также

[Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

