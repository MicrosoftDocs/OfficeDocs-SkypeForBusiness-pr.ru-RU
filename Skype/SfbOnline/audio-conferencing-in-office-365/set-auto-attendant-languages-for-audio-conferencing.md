---
title: Набор auto attendant языков для аудиоконференции
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Узнайте, как выбрать аудиоконференций auto автосекретаря языков для номера аудиоконференций.
ms.openlocfilehash: 44c05f081115ddf50eefd8df97765b3cbd82ef56
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703771"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Набор auto attendant языков для аудиоконференции

Автосекретарь конференции для Скайп для бизнеса и рабочих групп Microsoft можно приветствовать звука звонящих в некоторых языков при их присоединении к собранию.
  
Выберите один основной язык и до четырех дополнительных языков. Первым используется основной язык, заданная и что выбрать дополнительные языки будут использовать автосекретаря. 
  
> [!NOTE]
>  Языки можно настроить на внутреннем звука номеров доступа только.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Настройка конференц-связи auto attendant языков

![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**

1. В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.

2. Выберите номер телефона аудиоконференций из списка и в верхней части страницы, нажмите кнопку **Изменить**.

3. В области справа выберите нужный язык по умолчанию и любые дополнительные языки. 
 
    > [!NOTE]
    > По умолчанию и альтернативные языки, поддерживаемые указаны. Порядок, в котором можно выбрать их в списках будут порядок языков, представленных для вызывающих объектов. 

4. Нажмите кнопку **Применить**.

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **С помощью Скайп для бизнеса в Интернете**

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
  
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
