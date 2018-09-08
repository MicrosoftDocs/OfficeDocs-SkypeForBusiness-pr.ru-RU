---
title: Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Узнайте, как установить языки автоматического секретаря аудиоконференции для номера аудиоконференции в Skype для бизнеса Online.
ms.openlocfilehash: f7b7357d38941ba8d7e1f586f32daa8e02b29012
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882212"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online

> [!Note]
> Сведения об установке языков автоматического секретаря в Microsoft Teams см. в статье [Установка языков автоматического секретаря аудиоконференции в группах Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Автоматический секретарь аудиоконференции для Skype для бизнеса может приветствовать звонящих по телефону при их присоединении к собранию на нескольких различных языках.
  
Выберите один основной язык и до четырех дополнительных языков. Основной язык, который вы установили, автосекретарь будет использовать первым, а дополнительные языки будут использоваться автосекретарем в выбранном вами порядке. 
  
> [!NOTE]
>  Вы можете настроить языки только на внутренних телефонных номерах.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Установка языков автоматического секретаря конференции

Для выполнения этого действия вы должны войти в систему с правами [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) или [администратора Skype для бизнеса](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).
    
1. В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.
    
2. Выберите номер телефона аудиоконференций из списка и в области действий выберите пункт **задать языков**. 
    
3. На странице **Установка языков** выберите список **Основной язык**, чтобы просмотреть полный список доступных языков. При необходимости щелкните каждый из списков **Дополнительных языков**, чтобы выбрать дополнительный язык.
    
    > [!NOTE]
    > Перечисляются поддерживаемые основной и дополнительные языки Порядок, в котором можно выбрать их в списках будут порядок языков, представленных для вызывающих объектов. 
  
4. Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.
    
## <a name="want-else-should-i-know"></a>Хотите другим способом, должны знать?

- Со списком поддерживаемых языков для аудиоконференций можно ознакомиться в статье [Поддерживаемые языки аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Языки можно задать для персональных телефонных номеров, телефонных номеров совместного пользования.
    
- Список стран и регионов, в которых доступна аудиоконференция в Office 365 с помощью Microsoft в качестве поставщика, см. в статье [Номера телефонов для аудиоконференции](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell?

Для автоматизации этого шага, можно использовать командлеты [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Чтобы получить дополнительные сведения, обратитесь к разделу [С помощью Windows PowerShell для выполнения распространенных Скайп для бизнеса в Интернет задачи управления](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>См. также:

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
