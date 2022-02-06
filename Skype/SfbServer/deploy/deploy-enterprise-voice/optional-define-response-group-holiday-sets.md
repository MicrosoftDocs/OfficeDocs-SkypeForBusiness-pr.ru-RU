---
title: (Необязательный) Определение наборов праздников группы ответов в Skype для бизнеса
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Создание или изменение наборов праздников группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.
---

# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Необязательный) Определение наборов праздников группы ответов в Skype для бизнеса
 
Создание или изменение наборов праздников группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.
  
Параметры праздников служат для определения дней, в которые группа ответа закрыта для использования, а также для определения действия в эти дни. Набор праздников — это коллекция праздников, которая применяется к группе ответа.
  
> [!NOTE]
> Если рабочий процесс определяется как управляемый рабочий процесс, пользователь, которому была назначена роль CsResponseGroupManager, может изменять праздники для управляемых им рабочих процессов. 
  
### <a name="to-create-a-holiday-set"></a>Чтобы создать набор праздников

1. Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
3. Для каждого праздника, который следует определить, выполните следующую команду:
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Чтобы создать набор праздников, содержащий определенные праздники, выполните следующую команду:
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    В следующем примере приведен набор праздников, включающий два праздника:
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>См. также

[Разработка и создание рабочих процессов группы ответов в Skype для бизнеса](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)