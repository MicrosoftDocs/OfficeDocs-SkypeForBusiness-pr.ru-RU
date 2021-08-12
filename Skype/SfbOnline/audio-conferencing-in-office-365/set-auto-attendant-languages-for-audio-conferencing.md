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
ms.openlocfilehash: 044d05ec8b67f1e7732140a90c47b0666568fafe241fe3a45f2d02c46824e903
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326995"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Сведения об установке языков автоматического секретаря в Microsoft Teams см. в статье [Установка языков автоматического секретаря аудиоконференции в группах Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Автоматический секретарь аудиоконференции для Skype для бизнеса может приветствовать звонящих по телефону при их присоединении к собранию на нескольких различных языках.
  
Выберите один основной язык и до четырех дополнительных языков. Основной язык, который вы установили, автосекретарь будет использовать первым, а дополнительные языки будут использоваться автосекретарем в выбранном вами порядке. 
  
> [!NOTE]
>  Изменить можно только языки номеров аудиоконференций, которые имеют категорию Выделенный. Языки общего номера аудиоконференции изменить нельзя.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Установка языков автоматического секретаря конференции

Для выполнения этого шага [](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) [вы](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) должны быть глобальным Skype для бизнеса администратором.
    
1. В центре **Skype для бизнеса администрирования** на левой навигации перейдите на **устаревший портал**. На устаревшем портале выберите **Аудиоконференция** и щелкните **Мост Microsoft**.
    
2. Выберите номер телефона для аудиоконференции из списка и в области действий нажмите кнопку **Выбрать языки.** Изменить можно только языки выделенных номеров аудиоконференций.  
    
3. На странице **Установка языков** выберите список **Основной язык**, чтобы просмотреть полный список доступных языков. При необходимости щелкните каждый из списков **Дополнительных языков**, чтобы выбрать дополнительный язык.
    
    > [!NOTE]
    > Перечисляются поддерживаемые основной и дополнительные языки Порядок их выбора в списках будет порядок языков, представленных вызывателям. 
  
4. Нажмите кнопку **Сохранить**.
    
## <a name="want-else-should-i-know"></a>Хотите узнать больше?

- Со списком поддерживаемых языков для аудиоконференций можно ознакомиться в статье [Поддерживаемые языки аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Языки можно задать для персональных телефонных номеров, телефонных номеров совместного пользования.
    
- Список стран и регионов, в которых доступна аудиоконференция в Microsoft 365 или Office 365 майкрософт в качестве [](phone-numbers-for-audio-conferencing.md)поставщика, см. в Телефон для аудиоконференции.
    
## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell?

Для автоматизации этого шага вы можете использовать для этого [cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) и [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)
  
Дополнительные информации см. в [Windows PowerShell часто Skype для бизнеса управлением в Интернете.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
