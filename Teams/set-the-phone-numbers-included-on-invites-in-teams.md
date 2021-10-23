---
title: Указание номеров телефонов, которые можно включать в приглашения
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Выполните указанные здесь действия, чтобы создать телефонный номер по умолчанию, с помощью Microsoft Teams собрания.
ms.openlocfilehash: bef8575e1e799c63159bec5cbfb06c80f4af6c83
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536750"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Задание телефонных номеров, включаемых в приглашения, в Microsoft Teams

Аудиоконференция в Microsoft 365 и Office 365 позволяет пользователям в вашей организации создавать собрания Microsoft Teams, а затем разрешая им звонить на эти собрания по телефону.
  
Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.
  
> [!NOTE]
> Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Начальное назначение номеров телефонов, включенных в приглашения на собрание для новых пользователей

Номера телефонов, которые включаются в приглашения пользователей, включенных в аудиоконференцию, определяются платным номером по умолчанию и его настройками. Каждый параметр определяет, какой платный и бесплатный номер будут включены в приглашение на собрание определенного пользователя. Как было отмечено выше, каждое приглашение на собрание содержит один платный номер, один необязательный бесплатный номер и ссылку, которая открывает полный список всех телефонных номеров для звонков, которые можно использовать для звонков на собрание.

Для нового пользователя платные номера для аудиоконференации по умолчанию устанавливаются в зависимости от расположения использования, за установленного в центре администрирования Microsoft 365 пользователя, если для пользователя включена служба аудиоконференации. Если в мосте конференц-залов есть платный номер, соответствующий стране пользователя, он будет автоматически назначен платным номером по умолчанию. Если такой учетной записи нет, платный номер по умолчанию для моста конференц-залов будет назначен платным номером по умолчанию для пользователя.  

После включения службы аудиоконференций администратор клиента может в любой момент изменить платные и бесплатные номера телефонов пользователя по умолчанию.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Настройка или изменение номера телефона аудиоконференции по умолчанию для организатора или пользователя собрания

 **С помощью Центра администрирования Microsoft Teams**

Вы должны быть администратором службы Teams, чтобы вносить эти изменения. Сведения о получении ролей и разрешений администратора см. в статье [Управление Teams с помощью ролей администратора Teams](./using-admin-roles.md).

1. Войдите в центр Microsoft Teams администрирования.

2. В левой области навигации щелкните **Пользователи**.

    ![Выбор пользователей в центре Microsoft Teams администрирования.](media/Admin-users.png)

3. Щелкните имя пользователя в списке доступных пользователей.

4. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

    ![Нажмите кнопку Изменить рядом с кнопкой Аудиоконференция.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Используйте поля **Платный номер** **или** Бесплатный номер, чтобы ввести номера для пользователя.

> [!IMPORTANT]
> При изменении параметров аудиоконференции пользователя повторяющиеся и будущие собрания Microsoft Teams должны быть обновлены и отправлены участникам.

## <a name="want-to-use-windows-powershell"></a>Хотите использовать Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Шесть причин использовать Windows PowerShell для управления Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Чтобы настроить или изменить номер телефона для аудиоконференции по умолчанию для организатора собрания или пользователя с помощью [Microsoft Teams PowerShell,](/powershell/module/teams/?view=teams-ps)задате для параметра **`ServiceNumber`** **`TollFreeServiceNumber`** [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) один из доступных номеров.

## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Изменение номеров телефонов для моста аудиоконференций](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
