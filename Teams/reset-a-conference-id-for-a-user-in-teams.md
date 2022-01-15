---
title: Сброс идентификатора конференции для пользователя в Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Узнайте, как сбросить ИД конференции пользователя в Microsoft Teams и получить ссылки на средства обновления собраний и миграции.
ms.openlocfilehash: 55dc8935d191f518ca353d4b384b36e205f5c584
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056049"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Сброс идентификатора конференции для пользователя в Microsoft Teams

Динамический ИД конференции включается в нижней части приглашений на собрание, а также номера телефонов для телефонного звонка, которые могут использоваться звоня на собрание. Когда пользователь наберет номер телефона, автозаводщик собрания попросит вызывающего пользователя ввести этот номер конференции, чтобы он принял участие в собрании.
  
> [!NOTE]
> Коды конференции создаются автоматически, от 7 до 9 цифр и устанавливаются при включлении аудиоконференции для пользователя. **Статические ИД конференции не поддерживаются.**

## <a name="resetting-the-conference-id-for-a-user"></a>Сброс ИД конференции для пользователя

В Центре Microsoft Teams администрирования:

1. В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.

2. Нажмите **кнопку Изменить**.

3. В **области Аудиоконференции щелкните** **Сбросить ИД конференции**.

4. В **окне Сброс ИД конференции** нажмите кнопку **Сброс**. A conference ID will be automatically created and an email sent to the user with the new conference ID. По умолчанию сообщения отправляются пользователям, но это можно отключить.

> [!NOTE]
> После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. Во многих случаях это сообщение отправляется на основной адрес электронной почты Microsoft 365 или Office 365 почтовый ящик. Сообщение электронной почты содержит новый ИД конференции, номера телефонов для телефонного звонка по умолчанию и инструкции по обновлению существующих собраний.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Дополнительные сведения

- Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и  телефонные номера для телефонного  звонка, щелкнув Отправить сведения о конференции по электронной почте пользователю в разделе Аудиоконференции. ПИН-код не отправляется.

- 7–9-значный код конференции создается службой Teams конференции. Изменить ее длину нельзя.

- После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.

- После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps&preserve-view=true).

## <a name="related-topics"></a>Связанные разделы

[Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md)
