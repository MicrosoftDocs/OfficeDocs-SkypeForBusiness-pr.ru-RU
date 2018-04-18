---
title: Peer-to-peer activity report
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.custom:
- Reporting
description: 'Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. '
ms.openlocfilehash: ad2e9745d68a3c47e60aa03f957054a1eeef1deb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="peer-to-peer-activity-report"></a>Peer-to-peer activity report

The new Office 365 **Reports** dashboard shows you the activity overview across the Office 365 products in your organization. It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product. For example, you can use the **Skype for Business peer-to-peer activity** report to see how much your users are using IM, audio, video, application sharing, and transferring files. 

Check out the [Reports overview](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
This report, along with the other Skype for Business reports, gives you details on activity across your organization. Эти сведения полезны при анализе, планировании и принятии других решений на уровне организации. 
  
> [!NOTE]
> Вы можете просмотреть все отчеты Skype для бизнеса, если войдете в Центр администрирования Office 365 в качестве администратора. 
  
## <a name="how-to-get-to-the-skype-for-business-peer-to-peer-activity-report"></a>Получение отчета об одноранговых сеансах в Skype для бизнеса

1. Go to the **Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business peer-to-peer activity** on the **Select a report list** on the left. Or, click the **Skype for Business activity** widget and then click **Skype for Business peer-to-peer activity** on the **Skype for Business activity** list.
    
     ![Skype peer to peer menu selected](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > Для некоторых подписок на Office 365 могут быть доступны не все продукты и отчеты об активности, показанные в этой статье. 
  
## <a name="interpret-the-skype-for-business-peer-to-peer-activity-report"></a>Интерпретация данных в отчете об одноранговых сеансах в Skype для бизнеса

Чтобы получить представление об одноранговых сеансах в Skype для бизнеса, просмотрите диаграммы **Действие**, **Пользователи** и **Минуты**.
  
![Skype peer to peer report with callouts.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
***
![Number 1](../images/sfbcallout1.png)<br/>В отчете **Одноранговые сеансы в Skype для бизнеса** можно отследить тенденции за последние 7, 30, 90 и 180 дней.

    > [!Note]
    > If you click into the details of a specific day, the table will only show data for the 30 days up to the date when the report was generated.
***
![Number 2](../images/sfbcallout2.png)<br/>Для каждого отчета указывается дата создания. The reports usually reflect a 24- to 48-hour latency from time of activity. 
***
![Number 3](../images/sfbcallout3.png)<br/>На интерактивной диаграмме **Активность** отображаются тенденции использования, а также общее число сеансов по типу сеанса, проводимых в вашей организации. It will show you the total number and types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** sessions across your organization. 
***
![Number 4](../images/sfbcallout4.png)<br/>На интерактивной диаграмме **Пользователи** отображаются тенденции использования, а также число уникальных пользователей, которые принимали участие в одноранговых сеансах, проводимых в вашей организации. It will show you the total number of users along with the types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** in peer-to-peer sessions.
***
![Number 5](../images/sfbcallout5.png)<br/>На интерактивной диаграмме **Минуты** отображаются тенденции использования, а также общая длительность проводимых пользователями одноранговых сеансов с использованием аудио- и видеосвязи. Здесь отображается общая продолжительность участия пользователей в одноранговых сеансах с типом **Аудио** и **Видео**.  
***
![Number 6](../images/sfbcallout6.png)<br/>На каждой диаграмме представлены горизонтальная (X) и вертикальная (Y) оси. 
*    На диаграмме **Активность** по оси Y указывается общее число сеансов с использованием услуг обмена мгновенными сообщениями, аудио- и видеосвязи, общего доступа к приложениям и передачи файлов, проведенных в вашей организации.
*    On the **Users** activity chart, the Y axis is the total number users that held IM, audio, video, application sharing, and transferring files sessions. 
*    На диаграмме **Минуты** по оси Y указывается общее число минут, затраченных пользователями в вашей организации на проведение одноранговых сеансов с использованием услуг аудио- и видеосвязи. 

На оси X обеих диаграмм представлен диапазон дат, выбранный для отчета.
***
![Number 7](../images/sfbcallout7.png)<br/>Вы можете отфильтровать ряд, который отображается на диаграмме, щелкнув элемент легенды. For example, on the **Activity** chart, click or tap **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** to see only the info related to each one. При выборе другого значения данные в таблице-сетке не меняются. 
***
![Number 8](../images/sfbcallout8.png)<br/>В таблице показаны сведения по всем одноранговым сеансам с разбивкой по пользователям. Здесь приводятся все пользователи, которым назначена лицензия на Skype для бизнеса, а также сведения об использовании ими одноранговых сеансов. При необходимости вы можете добавлять столбцы в таблицу.
*    **Имя пользователя**  это имя, указанное пользователем.
*    **Удален**  лицензия пользователя была удалена. <br/> <br/> **Note:**  Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. Столбец **Удален** указывает, что пользователь больше не является активным, но участвовал при формировании данных в отчете.  <br/><br/>
*    **Дата удаления**  это дата удаления лицензии пользователя. 
*    **Дата последнего действия (UTC)**  дата последнего действия, выполненного пользователем, в формате UTC.
*    **Мгновенные сообщения**  общее число одноранговых сеансов, проведенных пользователем.
*    **Аудио**  общее число одноранговых сеансов, где использовались услуги аудиосвязи.
*    **Видео**  общее число одноранговых сеансов, где использовались услуги видеосвязи.
*    **Общий доступ к приложениям**  общее число одноранговых сеансов общего доступа к приложениям.
*    **Передачи файлов**  общее число одноранговых сеансов передачи файлов.
*    **Время аудиосвязи (в минутах)**  общая продолжительность сеансов аудиосвязи в организации. 
*    **Время видеосвязи (в минутах)**  общая продолжительность сеансов видеосвязи в организации. 

Если политики организации не позволяют просматривать отчеты, в которых есть личные сведения пользователей, можно изменить параметр конфиденциальности для всех отчетов. Check out the **How do I hide user level details?** section in the [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
***
![Number 9](../images/sfbcallout9.png)<br/>Вы также можете экспортировать данные отчета в CSV-файл Excel, щелкнув или нажав **Экспорт**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)<br/>При этом данные всех пользователей будут экспортированы в формат, позволяющий сортировать и фильтровать их для дальнейшего анализа. Если у вас менее 2000 пользователей, вы можете сортировать и фильтровать значения в самой таблице отчета. Если пользователей больше 2000, для фильтрации и сортировки потребуется экспортировать данные.
***
![Number 10](../images/sfbcallout10.png)<br/>![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)<br/>Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.         
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Просмотр других отчетов по Skype для бизнеса

- [Отчет об активности в Skype для бизнеса](activity-report.md) . В этом отчете приводятся сведения об использовании одноранговых сеансов, а также организации пользователями конференций и участии в них.
    
- [Отчет об использованных клиентах Skype для бизнеса](device-usage-report.md) . В этом отчете представлены настольные (в том числе под управлением ОС Windows) и мобильные устройства, на которых установлено приложение Skype для бизнеса и которые используются для обмена мгновенными сообщениями и участия в собраниях.
    
- [Skype for Business conference organizer activity report](conference-organizer-activity-report.md) You can see how much your users are organizing conferences that use IM, audio/video, application sharing, Web, dial-in/out - 3rd party, and dial-in/out - Microsoft.
    
- [Skype for Business conference participant activity report](conference-participant-activity-report.md) You can see how many IM, audio/video, application sharing, Web and and dial-in/out conferencing conferences are being participated in.
    
- [Skype for Business users blocked report](users-blocked-report.md) You can see the users in your organization that have been blocked from making PSTN calls.
    
- [Skype for Business PSTN usage report](pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.
    
- [Skype for Business PSTN minute pools report](pstn-minute-pools-report.md) you can see the number of minutes consumed during the current month within your organization.

- [Skype for Business session details report](session-details-report.md) You can see details about individual user's call experiences.
    
## <a name="related-topics"></a>See also
[Отчеты об активности в Центре администрирования Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 