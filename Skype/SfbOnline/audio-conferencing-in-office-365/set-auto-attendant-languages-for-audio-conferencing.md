---
title: Задать auto attendant языков для аудиоконференции в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Узнайте, как выбрать аудиоконференций auto attendant языки, для номер аудиоконференций в Скайп для бизнеса в Интернет.
ms.openlocfilehash: 026a09290c6e008493784c0d883220e03d13559f
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490518"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Задать auto attendant языков для аудиоконференции в Скайп для бизнеса в Интернет

> [!Note]
> Сведения об установке языковых attendant автоматически в группах Microsoft [auto attendant языков для аудиоконференции в группах Microsoft](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)см.

Автосекретарь конференции для Скайп для бизнеса можно приветствовать звука звонящих в некоторых языков при их присоединении к собранию.
  
Выберите один основной язык и до четырех дополнительных языков. Первым используется основной язык, заданная и что выбрать дополнительные языки будут использовать автосекретаря. 
  
> [!NOTE]
>  Языки можно настроить на внутреннем звука номеров доступа только.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Настройка конференц-связи auto attendant языков

Должен быть [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) или [Скайп для бизнеса администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для выполнения этого шага.
    
1. В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.
    
2. Выберите номер телефона аудиоконференций из списка и в области действий выберите пункт **задать языков**. 
    
3. На странице **Установка языков** выберите **основной язык** списке, чтобы просмотреть полный список доступных языков. Если требуется, щелкните каждый из списков **дополнительных языков** , чтобы выбрать язык дополнительного.
    
    > [!NOTE]
    > Перечисляются основных и дополнительных языков, которые поддерживаются. Порядок, в котором можно выбрать их в списках будут порядок языков, представленных для вызывающих объектов. 
  
4. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.
    
## <a name="want-else-should-i-know"></a>Хотите другим способом, должны знать?

- Чтобы просмотреть список поддерживаемых языков для аудиоконференции, см [звук конференц-связи](audio-conferencing-supported-languages.md).
    
- Языки можно задать для выделенных, но не для общих телефонных номеров.
    
- Список страны или регионы, в которых доступен звук конференц-связи в Office 365 с помощью Microsoft в качестве поставщика, см [номера телефонов для аудиоконференции](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Необходимо использовать Windows PowerShell?

Для автоматизации этого шага, можно использовать командлеты [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Чтобы получить дополнительные сведения, обратитесь к разделу [С помощью Windows PowerShell для выполнения распространенных Скайп для бизнеса в Интернет задачи управления](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Связанные разделы

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
