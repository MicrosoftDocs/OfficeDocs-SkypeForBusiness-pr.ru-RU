---
title: Настройка голосовой почты телефонной системы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 891279af8416786ae25efd72450f1cd695b11df4
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2019
ms.locfileid: "30121014"
---
# <a name="set-up-phone-system-voicemail"></a>Настройка голосовой почты телефонной системы

Эта статья предназначена для [администрирования Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , чтобы настроить компонентов телефонной системы голосовой почты для всех пользователей в организации.

> [!NOTE]
> Голосовая почта телефонной системы поддерживает размещение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы обработки электронной почты. В качестве резервного механизма обеспечения работы сообщения голосовой почты телефонной системы могут повторно отправляться по протоколу SMTP. Это значит, что, если почтовый ящик пользователя находится в сторонней системе обработки электронной почты, сообщения будут приходить, но работоспособность службы и другие функции голосовой почты, такие как изменение приветствия и прочих настроек, не гарантируются.

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a>Полностью облачные среды: настройка голосовой почты телефонной системы

Для пользователей Skype для бизнеса Online и планов звонков голосовая почта телефонной системы настраивается автоматически и предоставляется пользователям после того, как вы назначите им лицензию на **телефонную систему** и номер телефона.
  
1. Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** . Кроме того, может потребоваться приобрести лицензии Exchange Online. См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе. After you do that, they will be able to receive voicemail messages!
    
3. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

## <a name="phone-system-with-on-premises-environments"></a>Телефонная система с локальными средами

В этом разделе приводятся сведения о настройке службы голосовой почты телефонной службы для работы в локальных средах планов звонков.
  
1. Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** . Необходимо также приобрести лицензии Exchange Online. См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.
    
3. Следуйте инструкциям в разделе **Включить пользователей для телефонной системы голосовой связи и голосовой почты служб** [Скайп настроить соединитель Cloud Business Edition руководство по](https://technet.microsoft.com/library/mt605228.aspx).

4. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

5. Сведения о настройке доставки сообщений голосовой почты Azure для пользователей телефонной системы, имеющих локальный почтовый ящик, можно найти в статье [Azure PBX voicemail support for Exchange Server (Поддержка голосовой почты УАТС Azure для Exchange Server)](https://support.microsoft.com/kb/3195158).

6. Также прочтите и выполните шаги, описанные в следующих документов: [мастера гибридной конфигурации](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

> [!IMPORTANT]
> Не удается создать новый экземпляр политики для транскрибирования и транскрибирования сквернословие маскирование с помощью командлета **New-CsOnlineVoiceMailPolicy** , и вы не можете удалить существующего экземпляра политики с помощью командлета **Remove-CsOnlineVoiceMailPolicy** .

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы просмотреть все экземпляры политики голосовой почты доступны, можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Выключение транскрибирования для организации

Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Включение транскрибирования маскировки богохульства для вашей организации

Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации. Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Выключение транскрибирования для пользователя

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например транскрибирования голосовая почта включена для всех пользователей, следует назначить политики для отключения транскрибирования для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

Для отключения транскрибирования для одиночного пользователя выполните команду:

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Включение транскрибирования маскировки богохульства для пользователя

Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

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
[Настройка Skype для бизнеса Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Возможности телефонной системы в Office 365](here-s-what-you-get-with-phone-system.md)


