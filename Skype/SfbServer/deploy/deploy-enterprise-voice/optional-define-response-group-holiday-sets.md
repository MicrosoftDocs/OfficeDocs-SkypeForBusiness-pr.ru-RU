---
title: Определение набора праздников группы ответа в Skype для бизнеса 2015 (необязательно)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Создание и изменение наборах праздников ответа, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: b176a90b11957128fe485cd608608798d6ff6365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>Определение набора праздников группы ответа в Skype для бизнеса 2015 (необязательно)
 
Создание и изменение наборах праздников ответа, в Скайп Business Server корпоративной голосовой связи.
  
Параметры праздников служат для определения дней, в которые группа ответа закрыта для использования, а также для определения действия в эти дни. Набор праздников — это коллекция праздников, которая применяется к группе ответа.
  
> [!NOTE]
> Если рабочий процесс определяется как управляемый рабочий процесс, пользователь, которому была назначена роль CsResponseGroupManager, может изменять праздники для управляемых им рабочих процессов. 
  
### <a name="to-create-a-holiday-set"></a>Чтобы создать набор праздников

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Для каждого праздника, который следует определить, выполните следующую команду:
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Чтобы создать набор праздников, содержащий определенные праздники, выполните следующую команду:
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    В следующем примере приведен набор праздников, включающий два праздника:
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>См. также

#### 

[Проектирование и создание рабочих процессов для группы ответа в Скайп для бизнеса 2015](designing-and-creating-response-group-workflows.md)
#### 

[Командлет New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)
  
[Командлет New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)

