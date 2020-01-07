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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Сведения о том, как настроить облачную голосовую почту для пользователей. '
ms.openlocfilehash: e0ddeac2230d057ac64237a6728e8e707f5d8958
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952482"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="71612-103">Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="71612-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="71612-104">Эта статья относится к [администратору Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , который хочет настроить функцию голосовой почты в облаке для всех пользователей компании.</span><span class="sxs-lookup"><span data-stu-id="71612-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="71612-105">Облачная Голосовая почта поддерживает депозит сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы электронной почты.</span><span class="sxs-lookup"><span data-stu-id="71612-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="71612-106">Облачные среды: Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="71612-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="71612-107">Для пользователей Skype для бизнеса Online и планов звонков пользователи, облачная Голосовая почта автоматически настраиваются и подготавливаются для пользователей после назначения им лицензии на **телефонную систему** и номера телефона.</span><span class="sxs-lookup"><span data-stu-id="71612-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="71612-108">Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** .</span><span class="sxs-lookup"><span data-stu-id="71612-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="71612-109">Кроме того, может потребоваться приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="71612-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="71612-110">Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="71612-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="71612-111">[Назначение и удаление лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="71612-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="71612-112">После этого они смогут получать сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="71612-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="71612-p103">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="71612-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="71612-115">Телефонная система с локальными средами</span><span class="sxs-lookup"><span data-stu-id="71612-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="71612-116">Ниже приведены сведения о настройке облачной голосовой почты для работы в локальных средах планов звонков.</span><span class="sxs-lookup"><span data-stu-id="71612-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="71612-117">Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** .</span><span class="sxs-lookup"><span data-stu-id="71612-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="71612-118">Необходимо также приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="71612-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="71612-119">Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="71612-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="71612-120">[Назначение и удаление лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="71612-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="71612-121">Следуйте указаниям, соответствующим локальному решению по КОММУТИРУЕМой телефонной связи, развернутому для пользователей.</span><span class="sxs-lookup"><span data-stu-id="71612-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="71612-122">Для облачного соединителя Edition выполните инструкции в разделе **Включение пользователей для голосовой связи и служб голосовой почты** в [руководстве Настройка Skype для бизнеса Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="71612-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="71612-123">Для звонков по КОММУТИРУЕМой телефонной связи с помощью Skype для бизнеса Server [установите флажок включить локальные пользователи для предприятий](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="71612-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="71612-124">Для прямой маршрутизации в Teams настройте [прямую маршрутизацию](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail), следуя указаниям **Настройка номера телефона и включения корпоративной голосовой и голосовой почты** .</span><span class="sxs-lookup"><span data-stu-id="71612-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="71612-p106">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="71612-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="71612-127">Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователя по протоколу SMTP с помощью Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="71612-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="71612-128">Чтобы успешно допустить передачу этих сообщений, убедитесь, что соединители Exchange настроены правильно для серверов Exchange и Exchange Online Protection. [Настройка потока обработки почты с помощью соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="71612-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="71612-129">Для включения функций голосовой почты, таких как Настройка приветствий и визуальная голосовая почта в клиентах Skype для бизнеса, требуется подключение с Office 365 к почтовому ящику Exchange Server с помощью веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="71612-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="71612-130">Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности OAuth Exchange, описанный в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), или запустите мастер гибридного развертывания Exchange из Exchange 2013 CU5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="71612-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="71612-131">Кроме того, необходимо настроить интеграцию и OAuth между Skype для бизнеса Online и Exchange Server, описанными в разделе [Настройка интеграции и OAuth для Skype для бизнеса Online и Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="71612-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="71612-132">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="71612-132">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="71612-133">Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики вызова Microsoft Teams может также привести к отключению службы голосовой почты в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="71612-133">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="71612-134">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="71612-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="71612-135">Сообщения голосовой почты, полученные от пользователей вашей организации, транскрибед в регионе, где размещается клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="71612-135">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="71612-136">Область, в которой размещен ваш клиент, может не совпадать с регионом, в котором находится пользователь, получивший сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="71612-136">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="71612-137">Чтобы просмотреть область, в которой размещен ваш клиент, перейдите на страницу [профиля организации](https://go.microsoft.com/fwlink/p/?linkid=2067339) и нажмите кнопку **Просмотреть сведения** рядом с областью **данных**.</span><span class="sxs-lookup"><span data-stu-id="71612-137">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71612-138">Вы не можете создать новый экземпляр политики для транскрипции и ненормативную лексику с помощью командлета **New-ксонлиневоицемаилполици** , и вы не можете удалить существующий экземпляр политики с помощью командлета **Remove-ксонлиневоицемаилполици** .</span><span class="sxs-lookup"><span data-stu-id="71612-138">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="71612-139">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="71612-139">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="71612-140">Для просмотра всех доступных экземпляров политики голосовой почты можно использовать командлет [Get-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="71612-140">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="71612-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="71612-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Результаты окна Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="71612-143">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="71612-143">Turning off transcription for your organization</span></span>

<span data-ttu-id="71612-p111">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="71612-p111">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="71612-146">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="71612-146">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="71612-147">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="71612-147">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="71612-148">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="71612-148">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="71612-149">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="71612-149">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="71612-150">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="71612-150">Turning off transcription for a user</span></span>

<span data-ttu-id="71612-151">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="71612-151">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="71612-152">Например, если для всех пользователей включена транскрипция голосовой почты, вы можете назначить политике отключение транскрипции для определенного пользователя с помощью командлета [Grant-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="71612-152">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="71612-153">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="71612-153">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="71612-154">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="71612-154">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="71612-155">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="71612-155">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="71612-156">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="71612-156">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="71612-p114">Служба голосовой почты в Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="71612-p114">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="71612-159">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="71612-159">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="71612-p115">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="71612-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="71612-162">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="71612-162">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="71612-163">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="71612-163">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="71612-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="71612-164">Related topics</span></span>
[<span data-ttu-id="71612-165">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="71612-165">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="71612-166">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="71612-166">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="71612-167">Планирование миграции Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="71612-167">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


