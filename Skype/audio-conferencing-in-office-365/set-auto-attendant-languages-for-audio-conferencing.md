---
title: "Набор auto attendant языков для аудиоконференции"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Узнайте, как выбрать аудиоконференций auto автосекретаря языков для номера аудиоконференций."
ms.openlocfilehash: 1c6b5acda947b97d7bbfbd5888159b48bf5e95aa
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Набор auto attendant языков для аудиоконференции

Автосекретарь конференции для Скайп для бизнеса и рабочих групп Microsoft можно приветствовать звука звонящих в некоторых языков при их присоединении к собранию.
  
Выберите один основной язык и до четырех дополнительных языков. Первым используется основной язык, заданная и что выбрать дополнительные языки будут использовать автосекретаря. 
  
> [!NOTE]
>  Языки можно настроить на внутреннем звука номеров доступа только.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Настройка конференц-связи auto attendant языков

Должен быть [глобального администратора Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) или [Скайп для бизнеса администратора](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для выполнения этого шага.
  
1. Войдите в Office 365 под своей учебной или рабочей учетной записью.
    
2. Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.
    
3. В **Скайп по центру администрирования бизнеса**, в левой области переходов перейдите к **аудиоконференции**и нажмите кнопку **моста Microsoft**.
    
4. Выберите номер телефона аудиоконференций из списка и в области действий выберите пункт **задать языков**. 
    
5. На странице **Установка языков** выберите **основной язык** списке, чтобы просмотреть полный список доступных языков. Если требуется, щелкните каждый из списков **дополнительных языков** , чтобы выбрать язык дополнительного.
    
    > [!NOTE]
    > Перечисляются основных и дополнительных языков, которые поддерживаются. Порядок, в котором можно выбрать их в списках будут порядок языков, представленных для вызывающих объектов. 
  
6. Нажмите кнопку **Сохранить**.
    
## <a name="want-else-should-i-know"></a>Хотите другим способом, должны знать?

- Чтобы просмотреть список поддерживаемых языков для аудиоконференции, см [звук конференц-связи](audio-conferencing-supported-languages.md).
    
- Языки можно задать для выделенных, но не для общих телефонных номеров.
    
- Список страны или регионы, в которых доступен звук конференц-связи в Office 365 с помощью Microsoft в качестве поставщика, см [номера телефонов для аудиоконференции](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Необходимо использовать Windows PowerShell?

Для автоматизации этого шага, можно использовать командлеты [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) и [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Чтобы получить дополнительные сведения, обратитесь к разделу [С помощью Windows PowerShell для выполнения распространенных Скайп для бизнеса в Интернет задачи управления](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>См. также:

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](set-up-audio-conferencing.md)

