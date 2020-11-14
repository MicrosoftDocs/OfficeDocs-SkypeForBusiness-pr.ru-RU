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
description: 'Сведения о том, как настроить облачную голосовую почту для пользователей. '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031075"
---
# <a name="set-up-cloud-voicemail"></a>Настройка облачной голосовой почты

Эта статья предназначена для администраторов Microsoft 365 или Office 365, описанных в разделе [о ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) , которые хотят настроить облачную функцию голосовой почты для всех пользователей в Организации.

> [!NOTE]
> Облачная Голосовая почта поддерживает депозит сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы электронной почты. 

> [!NOTE]
> Когда представитель отвечает на звонок от имени представителя, уведомления не будут доступны в облачной голосовой почте. Пользователи могут получать уведомления о пропущенных звонках.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Облачные среды: Настройка облачной голосовой почты для пользователей онлайн-телефонной системы

Для пользователей телефонной системы в сети облачная Голосовая почта автоматически настраивается и предоставляется пользователям после назначения лицензии на **телефонную систему** пользователям. 

> [!NOTE]
> Для пользователей телефонной системы Skype для бизнеса с локальными предоставленными телефонными номерами может потребоваться включить размещенную голосовую почту с помощью [Set-CsUser-HostedVoicemail $true](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Настройка облачной голосовой почты для пользователей почтового ящика Exchange Server

Ниже приведены сведения о настройке облачной голосовой почты для работы с пользователями, которые подключены к Интернету для телефонной системы, но их почтовый ящик на сервере Exchange Server. 
  
1. Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователя по протоколу SMTP с помощью Exchange Online Protection. Чтобы успешно допустить передачу этих сообщений, убедитесь, что соединители Exchange настроены правильно для серверов Exchange и Exchange Online Protection. [Настройка потока обработки почты с помощью соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Для включения функций голосовой почты, таких как Настройка приветствий и визуальная голосовая почта в клиентах Skype для бизнеса, требуется 365 365 подключение к почтовому ящику Exchange Server с помощью веб-служб Exchange. Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности OAuth Exchange, описанный в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), или запустите мастер гибридного развертывания Exchange из Exchange 2013 CU5 или более поздней версии. Кроме того, необходимо настроить интеграцию и OAuth между Skype для бизнеса Online и Exchange Server, описанными в разделе [Настройка интеграции и OAuth для Skype для бизнеса Online и Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Настройка облачной голосовой почты для пользователей Skype для бизнеса Server

Чтобы настроить пользователей Skype для бизнеса Server для облачной голосовой почты, ознакомьтесь со сведениями [Планирование службы голосовой почты в облаке для локальных пользователей](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="enabling-protected-voicemail-in-your-organization"></a>Включение защищенной голосовой почты в Организации

Когда кто-то выходит за пределы голосовой почты для пользователя в вашей организации, она доставляется в почтовый ящик пользователя в виде вложения в сообщение электронной почты. Используя правила потока обработки почты для шифрования сообщений, вы можете предотвратить переадресацию голосовых сообщений другим получателям. Когда вы включаете защищенную голосовую почту, пользователи могут прослушивать защищенные голосовые сообщения, вызывая их в почтовый ящик голосовой почты или открывая сообщение в Outlook, Outlook в Интернете или в Outlook для Android или iOS. Защищенные голосовые сообщения не могут быть открыты в Skype для бизнеса.

Дополнительные сведения о шифровании сообщений можно найти в разделе [Шифрование электронной почты](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).

Чтобы настроить защищенную голосовую почту, выполните указанные ниже действия.

1. Войдите в систему с https://admin.microsoft.com помощью учетной записи с правами глобального администратора.
2. Нажмите кнопку **Показать все** , а затем перейдите в **центр администрирования**  >  **Exchange**.
3. В центре администрирования Exchange выберите правила **потока обработки почты**  >  **Rules**.
4. Нажмите кнопку **+** **Добавить** , а затем установите флажок **применять шифрование сообщений Office 365 и защиту прав к сообщениям**.
5. Укажите имя для нового правила потока обработки почты, а затем в разделе **Применить это правило, если** выбрать параметр **сообщение**  >  **содержит текст**  >  **голосовой почты**. Нажмите кнопку **ОК**.
6. В разделе **выполнить следующие действия** установите флажок **применить шифрование сообщений Office 365 и защиту прав на сообщение** , а затем нажмите **кнопку выбрать один из них**. В разделе **шаблон RMS** выберите пункт не **пересылать**. Нажмите кнопку **ОК** , а затем — **сохранить**.
    > [!NOTE]
    > Если список **шаблонов RMS** пуст, необходимо настроить шифрование сообщений. Дополнительные сведения о настройке шифрования сообщений можно найти в следующих статьях:
    > - [Настройка новых возможностей шифрования сообщений](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Настройка шаблонов для защиты данных Azure и управление ими](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [Параметр "не пересылать" для сообщений электронной почты](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a>Настройка политик голосовой почты в организации

> [!WARNING]
> Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики вызова Microsoft Teams может также привести к отключению службы голосовой почты в Skype для бизнеса.

Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).

Сообщения голосовой почты, полученные от пользователей вашей организации, transcribed в регионе, где размещается организация Microsoft 365 или Office 365. Область, в которой размещен ваш клиент, может не совпадать с регионом, в котором находится пользователь, получивший сообщение голосовой почты. Чтобы просмотреть область, в которой размещен ваш клиент, перейдите на страницу [профиля организации](https://go.microsoft.com/fwlink/p/?linkid=2067339) и нажмите кнопку **Просмотреть сведения** рядом с областью **данных**.

> [!IMPORTANT]
> Вы не можете создать новый экземпляр политики для транскрипции и ненормативную лексику с помощью командлета **New-CsOnlineVoiceMailPolicy** , и вы не можете удалить существующий экземпляр политики с помощью командлета **Remove-CsOnlineVoiceMailPolicy** .

Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты. Для просмотра всех доступных экземпляров политики голосовой почты можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .

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

Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации. Например, если для всех пользователей включена транскрипция голосовой почты, вы можете назначить политике отключение транскрипции для определенного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .

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
> Служба голосовой почты в Microsoft 365 и Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Помогите своим пользователям узнать о функциях голосовой почты Teams

У ваших пользователей есть следующие сведения о том, как управлять параметрами голосовой почты, а также с другими функциями для звонков в Teams.

- [Управление параметрами звонков в Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). В этой статье объясняется, как управлять всеми функциями вызова в Teams для конечных пользователей. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса

Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.

- [Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.

- [Обучение работе со Skype для бизнеса 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Возможности телефонной системы](here-s-what-you-get-with-phone-system.md)

[Планирование миграции Skype для бизнеса Server и Exchange Server](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
