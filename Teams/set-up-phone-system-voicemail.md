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
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Узнайте, как настроить облачную голосовую почту для пользователей. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662214"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья адресовна администратору Microsoft 365 или Office [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 365, как описано в статье "Роли администраторов, которые хотят настроить облачную голосовую почту для всех в компании".

> [!NOTE]
> Облачная голосовая почта поддерживает хранение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние почтовые системы. 

> [!NOTE]
> Когда делегат отвечает на звонок от имени представителя, в облачной голосовой почте уведомления недоступны. Пользователи могут получать уведомления о пропущенных звонках.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Облачные среды: настройка облачной голосовой почты для пользователей телефонной системы Online

Для пользователей телефонной системы Online облачная голосовая почта автоматически устанавливается  и устанавливается для пользователей после назначения им лицензии на телефонную систему. 

> [!NOTE]
> Пользователям телефонной системы Skype для бизнеса Online с номерами телефонов, предоставленными локально, может потребоваться включить услугу голосовой почты на сервере [Set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Настройка голосовой почты в облаке для Exchange Server пользователей почтовых ящиков

Ниже приводится информация о настройке облачной голосовой почты для работы с пользователями, которые находятся в сети для телефонной системы, но имеют свой почтовый ящик Exchange Server. 
  
1. Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователей через SMTP, маршрутный через Exchange Online Protection. Чтобы обеспечить их успешную доставку, убедитесь, что соединители Exchange Connectors правильно настроены на серверах Exchange Server и в службе Exchange Online Protection. [Используйте соединители для настройки потока почты.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Чтобы включить функции голосовой почты, такие как настройка приветствий и визуальной голосовой почты в клиентах Skype для бизнеса, требуется подключение Microsoft 365 или Office 365 к почтовому ящику сервера Exchange через веб-службы Exchange. Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности Exchange Oauth, описанный в описании функции "Настройка проверки подлинности [OAuth"](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)между организациями Exchange и Exchange Online, или запустить мастер гибридной конфигурации Exchange из Exchange 2013 CU5 или более новой. Кроме того, необходимо настроить интеграцию и Oauth между Skype для бизнеса Online и сервером Exchange, описанными в описании функций "Настройка интеграции" и ["OAuth"](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)между Skype для бизнеса Online и Exchange Server. 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Настройка облачной голосовой почты для пользователей Skype для бизнеса Server

Чтобы настроить пользователей сервера Skype для бизнеса для облачной голосовой почты, см. план обслуживания облачной голосовой почты для пользователей [локальной службы.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Включение защищенной голосовой почты в организации

Когда кто-то покидает сообщение голосовой почты пользователя в вашей организации, голосовая почта доставляется в почтовый ящик пользователя в виде вложения. Используя правила потока почты для применения шифрования сообщений, можно запретить их пересылку другим получателям. Если включить защищенную голосовую почту, пользователи смогут прослушивать защищенные сообщения голосовой почты, позвонив в свой почтовый ящик голосовой почты или открыв их в Outlook, Outlook в Интернете, а также в Outlook для Android или iOS. Защищенные сообщения голосовой почты нельзя открыть в Skype для бизнеса или Microsoft Teams.

Дополнительные сведения о шифровании сообщений см. в [теме "Шифрование электронной почты".](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Чтобы настроить защищенную голосовую почту, сделайте следующее:

1. Перейдите к учетной записи и войдите в нее с https://admin.microsoft.com разрешениями глобального администратора.
2. Выберите **"Показать все",** а затем перейдите в **центры администрирования**  >  **Exchange.**
3. В Центре администрирования Exchange выберите правила **потока обработки**  >  **почты.**
4. Выберите **+** **"Добавить",** а затем выберите "Применить шифрование сообщений **Office 365 и защиту прав к сообщениям".**
5. Введите имя для нового правила потока почты, а затем в списке "Применить это правило", если выберите свойства сообщения: "Голосовая почта".  >    >   Выберите **"ОК".**
6. В **области "Сделать следующее"** выберите "Применить шифрование сообщений **Office 365** и защиту прав к сообщению" и выберите **один из них.** В **области шаблона RMS выберите** **"Не переадваровываться".** Выберите **"ОК"** и **"Сохранить".**
    > [!NOTE]
    > Если список **шаблонов RMS** пуст, необходимо настроить шифрование сообщений. Дополнительные сведения о настройке шифрования сообщений см. в следующих статьях:
    > - [Настройка новых возможностей шифрования сообщений](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Настройка шаблонов и управление их использованием в Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Параметр "Не переад параметр" для сообщений электронной почты](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

> [!WARNING]
> Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики звонков Microsoft Teams также может отключить службу голосовой почты для пользователей Skype для бизнеса.

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Сообщения голосовой почты, полученные пользователями в вашей организации, транскрибются в регионе, где находится ваша организация Microsoft 365 или Office 365. Регион, в котором размещен клиент, может не быть регионом, в котором находится пользователь, получающий сообщение голосовой почты. Чтобы просмотреть регион размещения клиента, перейдите [](https://go.microsoft.com/fwlink/p/?linkid=2067339) на страницу профиля организации и нажмите кнопку "Просмотреть **сведения"** рядом с расположением **данных.**

> [!IMPORTANT]
> С помощью cmdlet **New-CsOnlineVoiceMailPolicy** нельзя создать новый экземпляр политики для транскрибации и транскрибации, а также удалить существующий экземпляр политики с помощью cmdlet **Remove-CsOnlineVoiceMailPolicy.**

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Чтобы увидеть все доступные экземпляры политик голосовой почты, используйте для этого cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)

 **PS C:\\> Get-CsOnlineVoicemailPolicy**
  
![Результаты окна Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a>Выключение транскрибирования для организации

Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Включение транскрибирования маскировки богохульства для вашей организации

Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации. Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a>Выключение транскрибирования для пользователя

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например, если транскрибация голосовой почты включена для всех пользователей, вы можете назначить политику для отключения транскрибации для конкретного пользователя с помощью cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)

Для отключения транскрибирования для одиночного пользователя выполните команду:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Включение транскрибирования маскировки богохульства для пользователя

Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).

Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> Служба голосовой почты в Microsoft 365 и Office 365 кэшетет политик голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Помощь пользователям в доступе к функциям голосовой почты Teams

Ниже данная информация содержит сведения об управлении настройками голосовой почты, а также другими функциями звонков в Teams.

- [Управление настройками параметров звонка в Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) В этой статье объясняется, как управлять всеми функциями звонков Teams для конечных пользователей. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса

Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.

- [Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.

- [Обучение работе со Skype для бизнеса 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Возможности телефонной системы](here-s-what-you-get-with-phone-system.md)

[Планирование миграции Skype для бизнеса Server и Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
