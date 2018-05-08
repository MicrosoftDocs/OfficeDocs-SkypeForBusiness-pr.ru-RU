---
title: Предоставление пользователям возможности записи собственного имени при присоединении к собранию
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: e183b133339022c9cfbdb58756584efb9b455550
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>Предоставление пользователям возможности записи собственного имени при присоединении к собранию

[] При настройке конференц-связи с телефонным подключением в Skype для бизнеса online вы получите телефонные номера и ресурс, который называется мостом для конференц-связи с телефонным подключением или для аудиоконференций. Мост для конференц-связи может содержать один или несколько телефонных номеров, которые могут быть как выделенными, так и общими.
  
Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.
  
## <a name="set-whether-callers-should-record-their-name"></a>Выбор необходимости записи имени вызывающей стороны

![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**

1. В левой области переходов, перейдите к **собраниям** > **Мостов конференции**. 

2. В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**. 

3. Включение или отключение **Включить запись собрание и выйти из уведомления, чтобы быть включенным**.

4. Нажмите кнопку **Применить**.


![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**
    
1. В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.
    
2. В разделе **Присоединение к собранию** включите параметр **Включить уведомления о входе и выходе из собрания**.
    
  - **Флажок установлен**  вызывающим сторонам будет выдан запрос о вводе имени перед входом в собрание. Выбрано по умолчанию.
    
  - **Флажок снят**  вызывающим сторонам не будет выдаваться запрос о вводе имени перед входом в собрание.
    
3. После внесения изменений нажмите кнопку **Сохранить**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Можно сэкономить время и автоматизировать процесс, используя командлет [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями и предоставлять им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упрощает выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
