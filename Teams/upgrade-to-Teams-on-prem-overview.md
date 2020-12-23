---
title: Обновление до Teams из локального развертывания Skype для бизнеса — Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Переход со Skype для бизнеса на Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578402"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Обновление Skype для бизнеса до Teams &mdash; для ИТ-администраторов

## <a name="overview"></a>Обзор

При переходе со Skype для бизнеса на Teams в некоторых организациях требуется постепенное обновление, которое планируется и управляется ИТ-отделом. Статьи в этом разделе в основном касаются ИТ-администраторов крупных организаций. Эти организации обычно являются локальной, но, возможно, они также являются крупными организациями Skype для бизнеса Online. Прежде чем читать эти статьи, не забудьте прочитать статью "Начало работы с обновлением [Teams"](upgrade-start-here.md) и ["Об обновлении".](upgrade-framework.md)


В следующих статьях вы можете перейти на следующую статью: 

- [Способы обновления](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Инструменты для управления обновлением](upgrade-to-teams-on-prem-tools.md)
- [Дополнительные соображения для организаций с локальной учетной записью Skype для бизнеса](upgrade-to-teams-on-prem-considerations.md)
- [Реализация перехода](upgrade-to-teams-on-prem-implement.md)
- [Вопросы, которые следует учесть при переходе на телефонную сеть общего перейти на телефонную сеть (ПС)](upgrade-to-teams-on-prem-pstn-considerations.md)

Кроме того, в следующих статьях описаны важные понятия обновления и принципы сосуществования.

- [Совместное сосуществование Teams и Skype для бизнеса](upgrade-to-teams-on-prem-coexistence.md)
- [Режимы сосуществования — ссылки](migration-interop-guidance-for-teams-with-skype.md)
- [Взаимодействие с клиентом Teams и соответствие режимам сосуществования](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>В этих статьях используются условия использования Skype для бизнеса Online, локального сервера Skype для бизнеса и Skype для бизнеса. Последний термин относится как к сетевым, так и к локальной версиям.

Прежде чем начать, вам следует знать, что пользователь, перенесенный в Teams, больше не использует клиент Skype для бизнеса, кроме звонков к собранию, которое проходит в Skype для бизнеса.  Все входящие чаты и звонки отправляются в клиент Teams пользователя, независимо от того, использует ли отправитель Teams или Skype для бизнеса. Новые собрания, организованные перенесенным пользователем, будут запланированы как собрания Teams. При попытке пользователя использовать клиент Skype для бизнеса, начало чатов и звонков блокируется.  Однако пользователь может (и должен) по-прежнему использовать клиент Skype для бизнеса, чтобы присоединяться к собраниям Skype для бизнеса, на которые он приглашен. (Старые клиенты Skype для бизнеса, которые были отправлены до 2017 г., не будут использовать TeamsUpgradePolicy. Убедитесь, что вы используете последнюю версию клиента Skype для бизнеса.)
 
Вы управляете переходом пользователя на Teams с помощью концепции [режима,](migration-interop-guidance-for-teams-with-skype.md)которое является свойством [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Пользователь, который был перенесен в Teams, как описано выше, находится в режиме TeamsOnly.  В организации, которая перейдет на Teams, конечная цель — переместить всех пользователей в режим TeamsOnly.

>[!NOTE]
>Пользователи с локальной учетной записью Skype для бизнеса не могут использовать TeamsOnly. Хотя эти пользователи могут [использовать Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)в режиме "О-ва", это не дает полный набор функций Teams, доступных в режиме TeamsOnly. Чтобы этих пользователей можно было использовать в TeamsOnly, их необходимо перенести в облако с помощью локального средства `Move-CsUser` Skype для бизнеса Server.

Хорошо. Давайте начнем.  Прежде всего нужно понять, какие методы [обновления доступны вам.](upgrade-to-teams-on-prem-upgrade-methods.md)







   

## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) 

[Настройка гибридного подключения между Skype для бизнеса Server и Microsoft 365 или Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Перемещение пользователей между локальной средой и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Настройка сосуществования и обновления](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Использование службы переноса собраний (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

