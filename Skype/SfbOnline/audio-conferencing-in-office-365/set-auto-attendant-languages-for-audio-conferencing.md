---
title: Набор auto attendant языков для аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Узнайте, как выбрать аудиоконференций auto автосекретаря языков для номера аудиоконференций.
ms.openlocfilehash: e7c4adb2129a737ec34e5641a9724bdab665cd23
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Набор auto attendant языков для аудиоконференции

Автосекретарь конференции для Скайп для бизнеса и рабочих групп Microsoft можно приветствовать звука звонящих в некоторых языков при их присоединении к собранию.
  
Выберите один основной язык и до четырех дополнительных языков. Первым используется основной язык, заданная и что выбрать дополнительные языки будут использовать автосекретаря. 
  
> [!NOTE]
>  Языки можно настроить на внутреннем звука номеров доступа только.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Настройка конференц-связи auto attendant языков

Должен быть [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) или [Скайп для бизнеса администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для выполнения этого шага.
  
1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.
    
4. Выберите номер телефона аудиоконференций из списка и в области действий выберите пункт **задать языков**. 
    
5. На странице **Установка языков** выберите **основной язык** списке, чтобы просмотреть полный список доступных языков. Если требуется, щелкните каждый из списков **дополнительных языков** , чтобы выбрать язык дополнительного.
    
    > [!NOTE]
    > Перечисляются основных и дополнительных языков, которые поддерживаются. Порядок, в котором можно выбрать их в списках будут порядок языков, представленных для вызывающих объектов. 
  
6. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.
    
## <a name="want-else-should-i-know"></a>Хотите другим способом, должны знать?

- Чтобы просмотреть список поддерживаемых языков для аудиоконференции, см [звук конференц-связи](audio-conferencing-supported-languages.md).
    
- Языки можно задать для выделенных, но не для общих телефонных номеров.
    
- Список страны или регионы, в которых доступен звук конференц-связи в Office 365 с помощью Microsoft в качестве поставщика, см [номера телефонов для аудиоконференции](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Необходимо использовать Windows PowerShell?

Для автоматизации этого шага, можно использовать командлеты [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Чтобы получить дополнительные сведения, обратитесь к разделу [С помощью Windows PowerShell для выполнения распространенных Скайп для бизнеса в Интернет задачи управления](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
