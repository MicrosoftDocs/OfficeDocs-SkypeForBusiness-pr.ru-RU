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
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163910"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Установка языков автоматического секретаря аудиоконференции в Skype для бизнеса Online

> [!Note]
> Сведения об установке языков автоматического секретаря в Microsoft Teams см. в статье [Установка языков автоматического секретаря аудиоконференции в группах Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Автоматический секретарь аудиоконференции для Skype для бизнеса может приветствовать звонящих по телефону при их присоединении к собранию на нескольких различных языках.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Изменить можно только языки номеров аудиоконференций, которые имеют категорию "Выделенный". Языки общего номера аудиоконференции изменить нельзя.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Установка языков автоматического секретаря конференции

Для выполнения этого шага [необходимо быть глобальным](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) администратором или администратором [Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для бизнеса.
    
1. В Центре **администрирования Skype для бизнеса** на левой навигации перейдите на **устаревший портал.** На устаревшем портале выберите "Аудиоконференция" и щелкните мост **Microsoft.** 
    
2. Выберите номер телефона для аудиоконференции из списка и в области действий нажмите кнопку "Выбрать **языки".** Изменить можно только языки выделенных номеров аудиоконференций.  
    
3. На странице **Установка языков** выберите список **Основной язык**, чтобы просмотреть полный список доступных языков. При необходимости щелкните каждый из списков **Дополнительных языков**, чтобы выбрать дополнительный язык.
    
    > [!NOTE]
    > Перечисляются поддерживаемые основной и дополнительные языки Порядок их выбора в списках будет порядок языков, которые перечислены вызывателям. 
  
4. Щелкните **Сохранить**.
    
## <a name="want-else-should-i-know"></a>Что еще мне нужно знать?

- Со списком поддерживаемых языков для аудиоконференций можно ознакомиться в статье [Поддерживаемые языки аудиоконференций](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Языки можно задать для персональных телефонных номеров, телефонных номеров совместного пользования.
    
- Список стран и регионов, в которых доступна аудиоконференция в Microsoft 365 или Office 365 с использованием Майкрософт в качестве поставщика, см. в области номеров телефонов для аудиоконференции. [](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell?

Для автоматизации этого шага можно использовать [cmdlets Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported.](https://go.microsoft.com/fwlink/?LinkId=617684)
  
Дополнительные узнать см. в [Windows PowerShell выполнения](https://go.microsoft.com/fwlink/?LinkId=525038) распространенных задач управления Skype для бизнеса Online
  
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
