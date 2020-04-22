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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Узнайте, как установить языки автоматического секретаря аудиоконференции для номера аудиоконференции в Skype для бизнеса Online.
ms.openlocfilehash: 34ed4ccee5239923f68b089ce14551fe43c32320
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776804"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online

> [!Note]
> Сведения об установке языков автоматического секретаря в Microsoft Teams см. в статье [Установка языков автоматического секретаря аудиоконференции в группах Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Автоматический секретарь аудиоконференции для Skype для бизнеса может приветствовать звонящих по телефону при их присоединении к собранию на нескольких различных языках.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Вы можете изменять только те языки, которые используются для нумерации видеоконференций в выделенной категории. Не удается изменить языки для номера конференц-связи с общим звуковым сопровождением.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Установка языков автоматического секретаря конференции

Это действие могут выполнять только администраторы [глобального администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) или [Skype для бизнеса](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .
    
1. В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к **устаревшему порталу**. На портале Legacy выберите пункт **Голосовая конференция**и выберите **Microsoft Bridge**.
    
2. Выберите номер телефона для голосовой конференции в списке и на панели действий нажмите кнопку **Выбрать языки**. Изменить языки выделенных номеров для голосовой конференции можно только.  
    
3. На странице **Установка языков** выберите список **Основной язык**, чтобы просмотреть полный список доступных языков. При необходимости щелкните каждый из списков **Дополнительных языков**, чтобы выбрать дополнительный язык.
    
    > [!NOTE]
    > Перечисляются поддерживаемые основной и дополнительные языки Порядок выбора элементов в списках — это порядок, в котором будут выводиться языки, представляемые для вызывающих абонентов. 
  
4. Нажмите кнопку **Сохранить**.
    
## <a name="want-else-should-i-know"></a>Хотите больше узнать?

- Со списком поддерживаемых языков для аудиоконференций можно ознакомиться в статье [Поддерживаемые языки аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Языки можно задать для персональных телефонных номеров, телефонных номеров совместного пользования.
    
- Список стран и регионов, в которых доступна аудиоконференция в Office 365 с помощью Microsoft в качестве поставщика, см. в статье [Номера телефонов для аудиоконференции](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell?

Чтобы автоматизировать этот шаг, можно использовать командлеты [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Дополнительные сведения можно найти в статье [Использование Windows PowerShell для выполнения стандартных задач управления в Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Статьи по теме

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
