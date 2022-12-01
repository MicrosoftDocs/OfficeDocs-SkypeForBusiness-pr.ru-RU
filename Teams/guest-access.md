---
title: Гостевой доступ в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.guestaccess.overview
- chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Гостевой доступ в Microsoft Teams позволяет командам в вашей организации сотрудничать с людьми, находящимися за пределами организации, предоставляя им доступ к командам и каналам.
ms.openlocfilehash: 399cd1c0aecb7377292810b26cd123873405f547
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198471"
---
# <a name="guest-access-in-microsoft-teams"></a>Гостевой доступ в Microsoft Teams

С помощью гостевого доступа можно предоставлять людям, находящимся за пределами организации, доступ к командам, документам в каналах, ресурсам, чатам и приложениям, при этом сохраняя контроль над своими корпоративными данными. См. статью [Настройка безопасной совместной работы с помощью Microsoft 365 и Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams). Гостевой доступ в Teams настраивается для всей организации и по умолчанию включен. Можно контролировать гостевой доступ к отдельным командам с помощью [меток конфиденциальности](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Если вы просто хотите найти людей из других организаций, позвонить им, пообщаться с ними в чате и провести с ними собрание, используйте [внешний доступ](manage-external-access.md).

Гость — это пользователь, у которого нет учебной или рабочей учетной записи, предоставленной вашей организацией. Например, к гостям могут относиться партнеры, продавцы, поставщики или консультанты. Любого пользователя, не состоящего в вашей организации, можно добавить в качестве гостя в Teams. Это означает, что любой пользователь с корпоративной учетной записью (т. е. учетной записью Azure Active Directory) или потребительской учетной записью электронной почты (Outlook.com, Gmail.com или других служб) может участвовать в Teams в качестве гостя с доступом к возможностям команд и каналов.

When you invite a guest to Teams, a guest account is created for them in Azure Active Directory and they are covered by the same compliance and auditing protection as other Microsoft 365 users. Guest access is subject to Azure AD and Microsoft 365 service limits.

The guest experience has limitations by design. For a full list of what a guest can and can't do in Teams, see [Guest access in Microsoft Teams](guest-experience.md).

> [!IMPORTANT]
> Guests follow Teams Org-wide settings for the coexistence Upgrade mode. This can't be changed.

Чтобы сравнить внешний доступ (федерацию) с гостевым доступом (и выбрать нужный), ознакомьтесь со статьей [Общение с пользователями из других организаций в Teams](communicate-with-users-from-other-organizations.md).

Shared channels offer an alternative to guest access, allowing you to invite people outside your organization without requiring a guest account in Azure AD. To compare guest access with shared channels, see [Plan external collaboration](/microsoft-365/solutions/plan-external-collaboration).

Чтобы настроить гостевой доступ, ознакомьтесь со статьей [Совместная работа с гостями в команде](/microsoft-365/solutions/collaborate-as-team). 

## <a name="set-up-guest-access"></a>Настройка гостевого доступа

Для предоставления гостевого доступа в Teams необходимо настроить параметры в Microsoft 365, а также Azure AD, Microsoft 365 Groups и SharePoint. Если вы готовы начать приглашать гостей в команды, см. следующие статьи.

- Чтобы настроить гостевой доступ в Teams для общего использования, см. статью [Совместная работа с гостями в команде](/microsoft-365/solutions/collaborate-as-team).
- Чтобы совместно работать с организацией-партнером, использующей Azure Active Directory, и позволить гостям самостоятельно регистрироваться для получения гостевого доступа, см. статью [Создание экстрасети B2B с управляемыми гостями](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Если вы администратор и у вас возникли проблемы с гостевым доступом в Microsoft Teams, выберите **Выполнить тесты** ниже, чтобы заполнить диагностику гостевого доступа в Центре администрирования Microsoft 365. Эти тесты проверят вашу конфигурацию и быстро порекомендуют дальнейшие действия, чтобы включить гостевой доступ для вашего клиента.
>> [!div class="nextstepaction"]
>> [Выполнить тесты: гостевой доступ](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>Как гость добавляется в команду

1. Владелец команды или администратор Microsoft 365 [добавляет гостя в команду](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Гость получает приветственное письмо от владельца команды, содержащее сведения о команде и о том, что следует ожидать после добавления в нее.
3. Гость принимает приглашение.
  Гости, у которых есть рабочая или учебная учетная запись в Azure Active Directory, могут принять приглашение и пройти проверку подлинности напрямую. Другим пользователям отправляется одноразовый секретный код для подтверждения их личности ([Проверка подлинности с помощью одноразового секретного кода](/azure/active-directory/external-identities/one-time-passcode) обязательно).
4. Приняв приглашение, гость сможет [использовать команды и каналы](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), просматривать сообщения каналов и отвечать на них, [получать доступ к файлам в каналах](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), участвовать в чатах, присоединяться к собраниям, вести совместную работу над документами и т. д. 

Гости в Teams четко определены. Имя гостя включает метку **(Гость)**, а канал содержит значок, указывающий на то, что в команде присутствуют гости. Дополнительные сведения см. в разделе [Взаимодействие с гостями](guest-experience.md).
  
Находясь внутри Teams, гости могут выходить из команды в любое время. Дополнительные сведения см. в разделе [Как покинуть команду?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Выход из команды не приведет к удалению гостевой учетной записи из каталога организации. Это должен сделать глобальный администратор Microsoft 365 или администратор Azure AD.

## <a name="licensing-for-guest-access"></a>Лицензии для гостевого доступа

Гостевой доступ можно использовать во всех подписках Microsoft 365 бизнес стандарт, Microsoft 365 корпоративный и Microsoft 365 для образования. Дополнительная лицензия Microsoft 365 не требуется. К гостям в Microsoft 365 применяется [модель выставления счетов для внешних удостоверений Azure AD](/azure/active-directory/b2b/licensing-guidance). В качестве гостей можно пригласить только людей из-за пределов вашей организации.

> [!NOTE]
> Преобразование гостевой учетной записи в учетную запись участника Azure AD или преобразование учетной записи участника Azure AD в гостевую не поддерживается в Teams.

## <a name="guest-access-reviews"></a>Проверка гостевого доступа

Чтобы создать проверку доступа для пользователей, состоящих в группе, или пользователей, назначенных приложению, можно использовать Azure AD. Создание повторяющихся проверок доступа может сэкономить ваше время. Если необходимо регулярно проверять пользователей, имеющих доступ к приложению, команде или группе, можно определить частоту этих проверок. 

Можно выполнять проверку гостевого доступа самостоятельно, просить гостей выполнить проверку их собственного доступа или просить владельца приложения или лицо, принимающее бизнес-решения, выполнить такую проверку. Для выполнения проверок гостевого доступа используйте портал Azure. Дополнительные сведения см. в статье [Управление гостевым доступом с помощью проверок доступа Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Статьи по теме

[Совместная работа с людьми, находящимися за пределами организации](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Запрет добавления гостей в определенную группу Microsoft 365 или команду Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Создание безопасной среды гостевого общего доступа](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Обращение в службу поддержки продуктов для бизнеса. Справка для администраторов](/microsoft-365/admin/contact-support-for-business-products)

[Настройка Teams с тремя уровнями защиты](/microsoft-365/solutions/configure-teams-three-tiers-protection)
