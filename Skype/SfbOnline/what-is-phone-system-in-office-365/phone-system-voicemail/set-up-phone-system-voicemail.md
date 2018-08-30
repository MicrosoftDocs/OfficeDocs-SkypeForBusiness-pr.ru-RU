---
title: Настройка голосовой почты телефонной системы
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
- Phone System
description: 'Узнайте, как настроить голосовую почту телефонной системы (облачная УАТС) для пользователей Skype для бизнеса. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252892"
---
# <a name="set-up-phone-system-voicemail"></a>Настройка голосовой почты телефонной системы

Эта статья предназначена для тех[администраторов Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), кто хочет настроить компонент голосовой почты телефонной системы для всех пользователей в организации.

> [!NOTE]
> Голосовая почта телефонной системы поддерживает размещение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы обработки электронной почты. В качестве резервного механизма обеспечения работы сообщения голосовой почты телефонной системы могут повторно отправляться по протоколу SMTP. Это значит, что, если почтовый ящик пользователя находится в сторонней системе обработки электронной почты, сообщения будут приходить, но работоспособность службы и другие функции голосовой почты, такие как изменение приветствия и прочих настроек, не гарантируются.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Полностью облачные среды: настройка голосовой почты телефонной системы

Для пользователей Skype для бизнеса Online и планов звонков голосовая почта телефонной системы настраивается автоматически и предоставляется пользователям после того, как вы назначите им лицензию на **телефонную систему** и номер телефона.

1. Если компонент телефонной системой не включен в план, может потребоваться приобрести лицензии дополнительного компонента **Phone System**. Кроме того, может потребоваться приобрести лицензии Exchange Online. См.[Лицензирование дополнительного компонента Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Назначение лицензий Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) и Exchange Online пользователям своей организации. После этого они смогут получать сообщения голосовой почты.

3. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

## <a name="phone-system-with-on-premises-environments"></a>Телефонная система с локальными средами

В этом разделе приводятся сведения о настройке службы голосовой почты телефонной службы для работы в локальных средах планов звонков.

1. Если компонент телефонной системой не включен в план, может потребоваться приобрести лицензии дополнительного компонента **Phone System**. Необходимо также приобрести лицензии Exchange Online. См.[Лицензирование дополнительного компонента Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

2. [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Назначение лицензий Skype для бизнеса и Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) и Exchange Online пользователям своей организации.

3. Для**Включения служб голосовой связи и голосовой почты телефонной системы для пользователей** следуйте инструкциям в разделе [руководстве по настройке Cloud Connector Edition Skype для бизнеса](https://technet.microsoft.com/en-us/library/mt605228.aspx).

4. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

5. Сведения о настройке доставки сообщений голосовой почты Azure для пользователей телефонной системы, имеющих локальный почтовый ящик, можно найти в статье [Azure PBX voicemail support for Exchange Server (Поддержка голосовой почты УАТС Azure для Exchange Server)](https://support.microsoft.com/en-us/kb/3195158).

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).

> [!IMPORTANT]
> С помощью командлета **New-CsOnlineVoiceMailPolicy** нельзя создать новый экземпляр политики для транскрибирования, а с помощью командлета **Remove-CsOnlineVoiceMailPolicy** нельзя удалить существующий экземпляр политики.

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы просмотреть все доступные экземпляры политик голосовой почты, можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

 **PS C:\\> Get-CsOnlineVoicemailPolicy**

![Результаты окна Get-CsOnlineVoiceMailPolicy.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a>Выключение транскрибирования для организации

Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Для этого выполните команду:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Включение транскрибирования маскировки богохульства для вашей организации

Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации. Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Для этого выполните команду:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Выключение транскрибирования для пользователя

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например, если транскрибирование голосовой почты включено для всех ваших пользователей, можно назначить политику, чтобы отключить транскрибирование для конкретного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Для отключения транскрибирования для одиночного пользователя выполните команду:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Включение транскрибирования маскировки богохульства для пользователя

Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).

Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Служба голосовой почты в Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса

Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.

- [Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.

- [Обучение работе со Skype для бизнеса 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Связанные разделы
[Настройка Skype для бизнеса Online](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[Возможности телефонной системы в Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


