---
title: Настройка escape-последовательности голосовой почты в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Сводка: Сведения о настройке отмены для голосовой почты в Скайп для Business Server 2015 с помощью Скайп для консоли Business Server.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Настройка escape-последовательности голосовой почты в Skype для бизнеса 2015
 
**Сводка:** Сведения о настройке отмены для голосовой почты в Скайп для Business Server 2015 с помощью Скайп для консоли Business Server.
  
Когда пользователь настраивает одновременных звонков на мобильный телефон, вызывающий объект обычно направляются в личную голосовую почту пользователя Если мобильный телефон является выключены, от батарей или вне диапазона. С Скайп Business Server связанной с бизнесом вызовы, направляемые в свои системы корпоративной голосовой почты выбранных пользователей. В частности можно настроить таймера, а если звонок был дан ответ с транспортной голосовой почты в интервал времени определенные, Скайп для Business Server будет отключиться от транспортной системы голосовой почты (и личную голосовую почту пользователя), при пользователя Оставшиеся конечных точек в корпоративной системе продолжить звонок. Таким образом, вызывающего автоматически маршрутизируются для корпоративной голосовой почты пользователя.
  
Эта настройка выполняется с помощью Скайп для командлета консоли Business Server, **Set-CsVoicePolicy**, на уровне политики голосовой связи, используя следующие параметры.
  
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

#### 

[Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и привилегии](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

