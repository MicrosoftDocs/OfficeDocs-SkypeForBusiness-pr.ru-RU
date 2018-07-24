---
title: (Необязательно) Группа ответа определение рабочих часов в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Создание или изменение группы ответа рабочих часов, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 3044d649bed946e14ff0459491c5df709d88c7f7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965648"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Необязательно) Группа ответа определение рабочих часов в Скайп для бизнеса 
 
Создание или изменение группы ответа рабочих часов, в Скайп Business Server корпоративной голосовой связи.
  
## <a name="defining-business-hours"></a>Определение рабочих часов

Настройки рабочих часов определяют, когда рабочий процесс доступен для ответа на вызовы, и задают процессы обработки вызовов, поступающих в нерабочее время. Администраторы групп ответа можно использовать командлет **New-CsRgsHoursOfBusiness** для создания предварительно заданных расписаний, которые можно использовать для любого числа групп ответа.
  
> [!TIP]
> При создании или изменение рабочего процесса, можно указать настраиваемое расписание, которое применяется только для этого рабочего процесса. Дополнительные сведения см [разработку и создание ответа рабочих процессов для группы в Скайп для бизнеса](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Если рабочий процесс был определен как управляемый, все пользователи, которым назначена роль CsResponseGroupManager, могут задавать и изменять рабочие часы для управляемых ими рабочих процессов. 
  
> [!IMPORTANT]
> Время для параметров в этих командлетах задается в 24-часовом формате (например, 20:00=8:00 PM). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>Создание предварительно определенной коллекции рабочих часов

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Для каждого уникального определяемого диапазона рабочих часов выполните команду:
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Чтобы создать коллекцию рабочих часов, использующую заданные диапазоны, выполните команду:
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    Ниже приведены примеры, в которых указываются рабочие часы с 9:00 до 17:00 для рабочих дней; с 8:00 до 10:00 и с 14:00 до 18:00 для суббот и не задаются рабочие часы для воскресений:
    
   ```
   $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>См. также

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[Новый CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)