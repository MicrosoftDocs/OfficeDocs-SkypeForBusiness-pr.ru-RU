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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Узнайте, как настроить голосовой почты в облаке для пользователей. '
ms.openlocfilehash: 827c52bf526ba84e4f571102354a096e2dc8e2f4
ms.sourcegitcommit: a46dad8dfc685534d81bb011f3c099c6f59ce2e0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "33882871"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="784c6-103">Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="784c6-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="784c6-104">Эта статья предназначена для [администрирования Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , чтобы настроить функции голосовой почты в облаке для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="784c6-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="784c6-105">Голосовая почта облачных поддерживает depositing сообщения голосовой почты только в почтовый ящик Exchange и не поддерживает все системы электронной почты сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="784c6-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="784c6-106">Только в облаке средах: Настройка голосовой почты в облаке</span><span class="sxs-lookup"><span data-stu-id="784c6-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="784c6-107">Для Скайп для бизнеса в Интернет и вызов планов пользователей автоматически настраивается и подготовлен для пользователей после назначения лицензий **Телефонной системой** и номер телефона для них голосовой почты в облаке.</span><span class="sxs-lookup"><span data-stu-id="784c6-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="784c6-108">Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="784c6-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="784c6-109">Кроме того, может потребоваться приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="784c6-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="784c6-110">См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="784c6-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="784c6-111">[Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="784c6-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="784c6-112">После этого они смогут получать сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="784c6-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="784c6-p103">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="784c6-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="784c6-115">Телефонная система с локальными средами</span><span class="sxs-lookup"><span data-stu-id="784c6-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="784c6-116">Сведения о настройке облачных голосовой почты для работы с локальной вызов Планирование сред — со следующими сведениями.</span><span class="sxs-lookup"><span data-stu-id="784c6-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="784c6-117">Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="784c6-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="784c6-118">Необходимо также приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="784c6-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="784c6-119">См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="784c6-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="784c6-120">[Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="784c6-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="784c6-121">Следуйте инструкциям, соответствия PSTN локального вызова решения, развертываемого для пользователей.</span><span class="sxs-lookup"><span data-stu-id="784c6-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="784c6-122">Для облачных соединителя Edition следуйте инструкциям, приведенным в разделе **Включить пользователей для службы телефонной системы голосовой связи и голосовая почта** [Настройка Скайп Edition соединитель Business Cloud руководство по](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="784c6-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="784c6-123">Для ТСОП Скайп при вызове для Business Server выполните перечисленные [Включить пользователей для корпоративной голосовой связи на собственных](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="784c6-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="784c6-124">Для групп прямой маршрутизации, приведенных в разделе **настроить номер телефона и включение корпоративной голосовой связи и голосовой почты** , [Настройка прямой](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="784c6-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="784c6-p106">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="784c6-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="784c6-127">Почтовых ящиков пользователей Exchange по протоколу SMTP направляться через Exchange Online Protection доставки сообщений голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="784c6-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="784c6-128">Чтобы включить успешную доставку сообщений, пожалуйста, убедитесь правильной настройке соединителей Exchange между серверами Exchange и Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="784c6-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="784c6-129">[Использование соединителей для настройки потока обработки почты](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="784c6-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="784c6-130">Для включения функции голосовой почты, например Настройка приветствия и visual голосовой почты в Скайп для клиентов, Business connectivity из Office 365 для почтовых ящиков Exchange server с помощью веб-служб Exchange является обязательным.</span><span class="sxs-lookup"><span data-stu-id="784c6-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="784c6-131">Для включения этого подключения необходимо настроить новый Exchange Oauth, описывающие протокол проверки подлинности в [проверки подлинности Настройка OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="784c6-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="784c6-132">Мастер гибридной Exchange выполнения из Exchange 2013 CU5 или более высокой версии будет автоматически обрабатывать требования в шаги 5 и 6.</span><span class="sxs-lookup"><span data-stu-id="784c6-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="784c6-133">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="784c6-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="784c6-134">Для Скайп для предприятий, отключение голосовой почты через группами Майкрософт, политика звонков может также отключить службу голосовой почты для вашей Скайп для коммерческих пользователей.</span><span class="sxs-lookup"><span data-stu-id="784c6-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="784c6-135">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="784c6-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="784c6-136">Не удается создать новый экземпляр политики для транскрибирования и транскрибирования сквернословие маскирование с помощью командлета **New-CsOnlineVoiceMailPolicy** , и вы не можете удалить существующего экземпляра политики с помощью командлета **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="784c6-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="784c6-137">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="784c6-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="784c6-138">Чтобы просмотреть все экземпляры политики голосовой почты доступны, можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="784c6-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="784c6-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="784c6-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Результаты окна Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="784c6-141">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="784c6-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="784c6-p110">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="784c6-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="784c6-144">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="784c6-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="784c6-145">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="784c6-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="784c6-146">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="784c6-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="784c6-147">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="784c6-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="784c6-148">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="784c6-148">Turning off transcription for a user</span></span>

<span data-ttu-id="784c6-149">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="784c6-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="784c6-150">Например транскрибирования голосовая почта включена для всех пользователей, следует назначить политики для отключения транскрибирования для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="784c6-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="784c6-151">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="784c6-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="784c6-152">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="784c6-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="784c6-153">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="784c6-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="784c6-154">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="784c6-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="784c6-p113">Служба голосовой почты в Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="784c6-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="784c6-157">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="784c6-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="784c6-p114">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="784c6-p114">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="784c6-160">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="784c6-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="784c6-161">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="784c6-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="784c6-162">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="784c6-162">Related topics</span></span>
[<span data-ttu-id="784c6-163">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="784c6-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="784c6-164">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="784c6-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="784c6-165">Планирование миграции Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="784c6-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


