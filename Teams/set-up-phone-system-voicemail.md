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
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="cd7e9-103">Настройка голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="cd7e9-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="cd7e9-104">Эта статья предназначена для [администрирования Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , чтобы настроить компонентов телефонной системы голосовой почты для всех пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="cd7e9-p101">Голосовая почта телефонной системы поддерживает размещение сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы обработки электронной почты. В качестве резервного механизма обеспечения работы сообщения голосовой почты телефонной системы могут повторно отправляться по протоколу SMTP. Это значит, что, если почтовый ящик пользователя находится в сторонней системе обработки электронной почты, сообщения будут приходить, но работоспособность службы и другие функции голосовой почты, такие как изменение приветствия и прочих настроек, не гарантируются.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="cd7e9-107">Полностью облачные среды: настройка голосовой почты телефонной системы</span><span class="sxs-lookup"><span data-stu-id="cd7e9-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="cd7e9-108">Для пользователей Skype для бизнеса Online и планов звонков голосовая почта телефонной системы настраивается автоматически и предоставляется пользователям после того, как вы назначите им лицензию на **телефонную систему** и номер телефона.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="cd7e9-109">Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="cd7e9-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="cd7e9-110">Кроме того, может потребоваться приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="cd7e9-111">См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-111">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="cd7e9-112">[Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="cd7e9-113">After you do that, they will be able to receive voicemail messages!</span><span class="sxs-lookup"><span data-stu-id="cd7e9-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="cd7e9-p104">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="cd7e9-116">Телефонная система с локальными средами</span><span class="sxs-lookup"><span data-stu-id="cd7e9-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="cd7e9-117">В этом разделе приводятся сведения о настройке службы голосовой почты телефонной службы для работы в локальных средах планов звонков.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="cd7e9-118">Если компонент телефонной системой не включена в план, может потребоваться приобрести лицензии дополнительный компонент **Телефонной системой** .</span><span class="sxs-lookup"><span data-stu-id="cd7e9-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="cd7e9-119">Необходимо также приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="cd7e9-120">См. [: Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-120">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="cd7e9-121">[Назначение и удаление лицензий на Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [группами Майкрософт назначение лицензий](assign-teams-licenses.md)и Exchange Online лицензии пользователям, находящимся в бизнесе.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="cd7e9-122">Следуйте инструкциям в разделе **Включить пользователей для телефонной системы голосовой связи и голосовой почты служб** [Скайп настроить соединитель Cloud Business Edition руководство по](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="cd7e9-p106">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="cd7e9-125">Сведения о настройке доставки сообщений голосовой почты Azure для пользователей телефонной системы, имеющих локальный почтовый ящик, можно найти в статье [Azure PBX voicemail support for Exchange Server (Поддержка голосовой почты УАТС Azure для Exchange Server)](https://support.microsoft.com/kb/3195158).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="cd7e9-126">Также прочтите и выполните шаги, описанные в следующих документов: [мастера гибридной конфигурации](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="cd7e9-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="cd7e9-127">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="cd7e9-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="cd7e9-128">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd7e9-129">Не удается создать новый экземпляр политики для транскрибирования и транскрибирования сквернословие маскирование с помощью командлета **New-CsOnlineVoiceMailPolicy** , и вы не можете удалить существующего экземпляра политики с помощью командлета **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="cd7e9-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="cd7e9-130">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="cd7e9-131">Чтобы просмотреть все экземпляры политики голосовой почты доступны, можно использовать командлет [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cd7e9-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="cd7e9-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="cd7e9-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="cd7e9-134">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="cd7e9-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="cd7e9-p108">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="cd7e9-137">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="cd7e9-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="cd7e9-138">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="cd7e9-139">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="cd7e9-140">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="cd7e9-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="cd7e9-141">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="cd7e9-141">Turning off transcription for a user</span></span>

<span data-ttu-id="cd7e9-142">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="cd7e9-143">Например транскрибирования голосовая почта включена для всех пользователей, следует назначить политики для отключения транскрибирования для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cd7e9-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="cd7e9-144">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="cd7e9-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="cd7e9-145">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="cd7e9-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="cd7e9-146">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="cd7e9-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="cd7e9-147">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cd7e9-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="cd7e9-p111">Служба голосовой почты в Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="cd7e9-150">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cd7e9-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="cd7e9-p112">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-p112">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="cd7e9-153">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="cd7e9-154">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="cd7e9-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="cd7e9-155">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cd7e9-155">Related topics</span></span>
[<span data-ttu-id="cd7e9-156">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cd7e9-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="cd7e9-157">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="cd7e9-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


