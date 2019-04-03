---
title: Настройка облачной голосовой почты
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Узнайте, как настроить голосовой почты в облаке для пользователей. '
ms.openlocfilehash: 26594c9d955cb21dc5751491e1857525660bdcae
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041936"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья предназначена для [администрирования Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , чтобы настроить функции голосовой почты в облаке для всех пользователей в организации.

> [!NOTE]
> Голосовая почта облачных поддерживает depositing сообщения голосовой почты только в почтовый ящик Exchange и не поддерживает все системы электронной почты сторонних производителей. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Только в облаке средах: Настройка голосовой почты в облаке

Для Скайп для бизнеса в Интернет и вызов планов пользователей автоматически настраивается и подготовлен для пользователей после назначения лицензий **Телефонной системой** и номер телефона для них голосовой почты в облаке.
  
1. Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** . Кроме того, может потребоваться приобрести лицензии Exchange Online. См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе. После этого они смогут получать сообщения голосовой почты.
    
3. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

## <a name="phone-system-with-on-premises-environments"></a>Телефонная система с локальными средами

Сведения о настройке облачных голосовой почты для работы с локальной вызов Планирование сред — со следующими сведениями.
  
1. Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** . Необходимо также приобрести лицензии Exchange Online. См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.
    
3. Следуйте инструкциям, соответствия PSTN локального вызова решения, развертываемого для пользователей. Для облачных соединителя Edition следуйте инструкциям, приведенным в разделе **Включить пользователей для службы телефонной системы голосовой связи и голосовая почта** [Настройка Скайп Edition соединитель Business Cloud руководство по](https://technet.microsoft.com/library/mt605228.aspx). Для ТСОП Скайп при вызове для Business Server выполните перечисленные [Включить пользователей для корпоративной голосовой связи на собственных](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Для групп прямой маршрутизации, приведенных в разделе **настроить номер телефона и включение корпоративной голосовой связи и голосовой почты** , [Настройка прямой](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)маршрутизации.

4. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

5. Почтовых ящиков пользователей Exchange по протоколу SMTP направляться через Exchange Online Protection доставки сообщений голосовой почты. Чтобы включить успешную доставку сообщений, пожалуйста, убедитесь правильной настройке соединителей Exchange между серверами Exchange и Exchange Online Protection. [Использование соединителей для настройки потока обработки почты](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

6. Для включения функции голосовой почты, например Настройка приветствие, конференц-связи доступа и visual голосовой почты, наличие подключения к Office 365 для почтовых ящиков Exchange server с помощью веб-служб Exchange является обязательным. Для включения этого подключения необходимо настроить новый Exchange Oauth, описывающие протокол проверки подлинности в [проверки подлинности Настройка OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) 

> [!NOTE]
> Мастер гибридной Exchange выполнения из Exchange 2013 CU5 или более высокой версии будет автоматически обрабатывать требования в шаги 5 и 6. 

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

> [!IMPORTANT]
> Не удается создать новый экземпляр политики для транскрибирования и транскрибирования сквернословие маскирование с помощью командлета **New-CsOnlineVoiceMailPolicy** , и вы не можете удалить существующего экземпляра политики с помощью командлета **Remove-CsOnlineVoiceMailPolicy** .

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы просмотреть все экземпляры политики голосовой почты доступны, можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Результаты окна Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
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


