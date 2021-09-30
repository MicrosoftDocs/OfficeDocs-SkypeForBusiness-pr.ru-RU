---
title: Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как разрешить или запретить анонимным абонентам присоединяться к собранию с помощью центра администрирования Skype for Business admin или путем использования сценария PowerShell. '
ms.openlocfilehash: d420acff8d5822aa4badd8980481d67bd2eae35b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013373"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Сведения о начале аудиоконференции без PIN-кода в Microsoft Teams см. в статье [Начало аудиоконференции по телефону без PIN-кода в Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Пользователям, которые будут проходить собрание по телефонной связи, может быть сложно слушать музыку в "Skype для бизнеса, так как организатор собрания еще не начал собрание. 
  
Если организатор собрания звонит на собрание, по умолчанию для начала собрания требуется ПИН-код. Вы можете настроить его таким образом, чтобы любой человек мог звонить на собрание, а пин-код не выводиться для начала собрания. Чтобы включить или отключить этот параметр для одного пользователя, используйте центр администрирования Skype для бизнеса.
  
ПИН-код не требуется организатору собрания, если кто-то начал собрание из Skype для бизнеса приложения. ПИН-код требуется только в том случае, если организатор собрания присоединяется к собранию по телефону. ПИН-код для собраний отправляется пользователю аудиоконференции, если ему назначена лицензия на аудиоконференцию и включена аудиоконференция.  [См.](send-an-email-to-a-user-with-their-dial-in-information.md) статью Отправка электронной почты пользователю со сведениями об аудиоконференциях и Электронные письма, которые автоматически отправляются пользователям при изменении их параметров аудиоконференции. [](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Разрешение и запрет присоединения анонимных абонентов к собранию
    
1. В центре **Skype для бизнеса** на левой навигации перейдите в меню Пользователи аудиоконференации  >  . 
    
2. Выберите пользователя в списке и в области действий нажмите кнопку **Изменить.** 
    
3. На странице свойств пользователя в области Параметры собрания **выберите** или отзовите параметр Разрешить неавентенным звонятелям быть первыми пользователями **на собрании. Если нет, то они будут ждать в "ожидании", пока пользователь,** который пройдет проверку подлинности, не присоединится.
    
4. Нажмите кнопку **Сохранить**. 


    
 **Использование Windows PowerShell**
  
- Выполните следующее: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

- Если вы хотите сбросить ПИН-код, см. сброс ПИН-кода [аудиоконференции.](reset-the-audio-conferencing-pin.md)
    
- Если анонимный доступ или требование ПИН-кода для начала собрания отключено:
    
  - Если собрание еще не началось (в собрании пока нет ни одного из них), вызываемой будет предложено, является ли он организатором; Если он даст ответ "Да", ему будет предложено ввести ПИН-код, а после ввода ПИН-кода начнется собрание, и пользователь присоединится к собранию.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.
    
- Если включен анонимный доступ или не требуется ПИН-код для начала собрания:
    
  - Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Так как параметр организатора отключен, собрание начнется, и анонимные звоняки присоединятся к собранию.
    
  - Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт по ссылке Скачивание и установка модуля [Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>См. также

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
