---
title: Ошибки общих каналов в Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Узнайте, как использовать исправления ошибок в общих каналах в Microsoft Teams.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024190"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Ошибки общих каналов в Microsoft Teams

Если пользователи видят сообщения об ошибках при попытке добавить пользователей из-за пределов организации в общие каналы, проверьте параметры, указанные в этой статье. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>Из-за политики администратора вы не можете добавлять внешних пользователей в канал. Для получения дополнительных сведений обратитесь к администратору.

Teams использует Группы Microsoft 365 для членства в команде. Параметры Группы Microsoft 365 должны быть включены, чтобы пользователи за пределами организации добавлялись в общий канал. Если пользователи видят эту ошибку, проверьте параметры Группы Microsoft 365 для пользователей за пределами организации.

Настройка Группы Microsoft 365 параметров для людей за пределами организации
1. В Центр администрирования Microsoft 365 области навигации слева разверните узел **"Параметры"**.
1. **Щелкните "Параметры организации"**.
1. В списке **щелкните Группы Microsoft 365**.
1. Убедитесь, что владельцы группы "Разрешить" добавлять людей за пределами **организации** в Группы Microsoft 365 в качестве  гостей, и установите флажки для доступа участников гостевой группы к содержимому группы.
1. Если вы внесли изменения, нажмите кнопку **"Сохранить изменения"**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>Из-за политики администратора вы не можете добавлять внешних пользователей в канал

Политики каналов Teams определяют, как пользователи могут взаимодействовать с общими каналами. Если пользователи видят это сообщение об ошибке, проверьте политику канала для этого пользователя.

Настройка политики для приглашения пользователей за пределами организации к общим каналам
1. В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам Teams > Teams.
1. Выберите политику, назначенную пользователю.
1. Убедитесь **, что включено приглашение** внешних пользователей в общие **каналы**.
1. Если вы внесли изменения, нажмите кнопку " **Применить"**.

Дополнительные сведения о политиках каналов Teams см. в разделе ["Управление политиками каналов" в Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>Вы не можете поделиться этим каналом с людьми из этой организации

Если пользователи видят эту ошибку, им запрещено предоставлять общий доступ к каналу пользователям из другой организации с помощью параметров межтенантного доступа Azure Active Directory. Это может быть вызвано параметрами входящего трафика в вашей организации или параметрами исходящего трафика в другой организации.

Проверка параметров входящего трафика для организации
1. В [Azure Active Directory выберите](https://aad.portal.azure.com) **внешние удостоверения**, а затем выберите **параметры межтенантного доступа**.
1. Выберите ссылку для входящего доступа для организации, которую вы хотите проверить.
1. На **вкладке "Прямое подключение B2B** " выберите **"Настройка параметров"**.
1. На вкладке "Внешние пользователи и группы"  убедитесь,  что выбраны параметры "Разрешить доступ" и "Все внешние пользователи и группы". Если вы выбрали "Выбрать внешних пользователей и группы **",** убедитесь, что приглашенный пользователь является участником выбранных групп.
1. Если вы внесли изменения, **выберите "Сохранить** " и закройте колонку " **Параметры входящего доступа** ".

Если пользователи по-прежнему видят ошибку, обратитесь к организации, с которой они совместно работают. Исходящие параметры этой организации могут запретить общий доступ к вашей организации. Сведения о настройке общих каналов между организациями см. в статье "Совместная работа с внешними участниками [в общем канале"](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>Не удалось найти совпадения. Убедитесь, что адрес электронной почты указан правильно, или обратитесь к администратору.

Если пользователи видят эту ошибку, Microsoft 365 не может найти указанный адрес электронной почты во внешней организации. Необходимо подтвердить адрес во внешней организации.
