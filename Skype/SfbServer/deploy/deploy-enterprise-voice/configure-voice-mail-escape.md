---
title: Настройка эвакуации голосовой почты в Skype для бизнеса
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
description: Сводка. Узнайте, как настроить выход голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106375"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Настройка эвакуации голосовой почты в Skype для бизнеса

**Сводка:** Узнайте, как настроить выход голосовой почты в Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов.

Когда пользователь настраивает одновременный звон на мобильный телефон, вызываемый пользователь обычно будет перенастроен на личную голосовую почту пользователя, если мобильный телефон отключен, отключен от батареи или вне диапазона. С помощью Skype для бизнеса Server пользователи могут выбрать маршрутные вызовы, связанные с бизнесом, в корпоративную систему голосовой почты. В частности, можно настроить timer, и если на вызов отвечает голосовая почта перевозчика в течение определенного времени, Skype для бизнеса Server отключается от системы голосовой почты оператора (и личной голосовой почты пользователя), в то время как оставшиеся конечные точки пользователя в корпоративной системе продолжают звонить. Таким образом, вызываемая почта автоматически перенанаписыется на корпоративную голосовую почту пользователя.

Эта конфигурация выполняется с помощью команды Команды управления Skype для **бизнес-серверов Set-CsVoicePolicy** на уровне голосовой политики со следующими параметрами.

### <a name="to-configure-voice-mail-escape"></a>Настройка побега голосовой почты

1. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**

2. Задайте следующие параметры для **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.

   - **PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.

## <a name="example"></a>Пример

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>См. также

[Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)