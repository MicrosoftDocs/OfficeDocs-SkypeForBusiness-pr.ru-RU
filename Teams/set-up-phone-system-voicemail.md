---
title: Настройка облачной голосовой почты
author: dstrome
ms.author: dstrome
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Сведения о том, как настроить облачную голосовую почту для пользователей. '
ms.openlocfilehash: 49f64f4b4cda9830bc189310efc26f39859009af
ms.sourcegitcommit: 1764aa53441b9de5a8cfa37be344657176ee5703
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2019
ms.locfileid: "34808027"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья относится к [администратору Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , который хочет настроить функцию голосовой почты в облаке для всех пользователей компании.

> [!NOTE]
> Облачная Голосовая почта поддерживает депозит сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы электронной почты. 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a>Облачные среды: Настройка облачной голосовой почты

Для пользователей Skype для бизнеса Online и планов звонков пользователи, облачная Голосовая почта автоматически настраиваются и подготавливаются для пользователей после назначения им лицензии на **телефонную систему** и номера телефона.
  
1. Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** . Кроме того, может потребоваться приобрести лицензии Exchange Online. Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий для Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации. После этого они смогут получать сообщения голосовой почты.
    
3. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

## <a name="phone-system-with-on-premises-environments"></a>Телефонная система с локальными средами

Ниже приведены сведения о настройке облачной голосовой почты для работы в локальных средах планов звонков.
  
1. Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** . Необходимо также приобрести лицензии Exchange Online. Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
2. [Назначение и удаление лицензий для Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации.
    
3. Следуйте указаниям, соответствующим локальному решению по КОММУТИРУЕМой телефонной связи, развернутому для пользователей. Для облачного соединителя Edition выполните инструкции в разделе **Включение пользователей для голосовой связи и служб голосовой почты** в [руководстве Настройка Skype для бизнеса Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx). Для звонков по КОММУТИРУЕМой телефонной связи с помощью Skype для бизнеса Server [установите флажок включить локальные пользователи для предприятий](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises). Для прямой маршрутизации в Teams настройте [прямую маршрутизацию](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail), следуя указаниям **Настройка номера телефона и включения корпоративной голосовой и голосовой почты** .

4. Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.

5. Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователя по протоколу SMTP с помощью Exchange Online Protection. Для успешной доставки этих сообщений убедитесь, что соединители Exchange настроены правильно между серверами Exchange и Exchange Online Protection. [Настройка потока обработки почты с помощью соединителей](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

6. Для включения функций голосовой почты, таких как Настройка приветствий и визуальная голосовая почта в клиентах Skype для бизнеса, требуется подключение с Office 365 к почтовому ящику Exchange Server с помощью веб-служб Exchange. Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности OAuth Exchange в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) . 

> [!NOTE]
> Мастер гибридной работы Exchange с Exchange 2013 CU5 или более поздней версии будет автоматически обрабатывать требования, описанные в действиях 5 и 6. 

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

> [!WARNING]
> Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики вызова Microsoft Teams может также привести к отключению службы голосовой почты в Skype для бизнеса.

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Сообщения голосовой почты, полученные от пользователей вашей организации, транскрибед в регионе, где размещается клиент Office 365. Область, в которой размещен ваш клиент, может не совпадать с регионом, в котором находится пользователь, получивший сообщение голосовой почты. Чтобы просмотреть область, в которой размещен ваш клиент, перейдите на страницу [профиля организации](https://go.microsoft.com/fwlink/p/?linkid=2067339) и нажмите кнопку **Просмотреть сведения** рядом с областью **данных**.

> [!IMPORTANT]
> Вы не можете создать новый экземпляр политики для транскрипции и ненормативной лексики с помощью командлета **New-ксонлиневоицемаилполици** , и вы не можете удалить существующий экземпляр политики с помощью командлета **Remove-ксонлиневоицемаилполици** . .

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Для просмотра всех доступных экземпляров политики голосовой почты можно использовать командлет [Get-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798311.aspx) .

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

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например, если для всех пользователей включена транскрипция голосовой почты, вы можете назначить политике отключение транскрипции для определенного пользователя с помощью командлета [Grant-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798309.aspx) .

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

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Возможности телефонной системы в Office 365](here-s-what-you-get-with-phone-system.md)

[Планирование миграции Skype для бизнеса Server и Exchange Server](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


