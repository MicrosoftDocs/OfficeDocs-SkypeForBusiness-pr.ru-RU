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
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="f7e4d-103">Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f7e4d-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="f7e4d-104">Эта статья относится к [администратору Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , который хочет настроить функцию голосовой почты в облаке для всех пользователей компании.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="f7e4d-105">Облачная Голосовая почта поддерживает депозит сообщений голосовой почты только в почтовом ящике Exchange и не поддерживает сторонние системы электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="f7e4d-106">Облачные среды: Настройка облачной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f7e4d-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="f7e4d-107">Для пользователей Skype для бизнеса Online и планов звонков пользователи, облачная Голосовая почта автоматически настраиваются и подготавливаются для пользователей после назначения им лицензии на **телефонную систему** и номера телефона.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="f7e4d-108">Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="f7e4d-109">Кроме того, может потребоваться приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="f7e4d-110">Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="f7e4d-111">[Назначение и удаление лицензий для Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="f7e4d-112">После этого они смогут получать сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="f7e4d-p103">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="f7e4d-115">Телефонная система с локальными средами</span><span class="sxs-lookup"><span data-stu-id="f7e4d-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="f7e4d-116">Ниже приведены сведения о настройке облачной голосовой почты для работы в локальных средах планов звонков.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="f7e4d-117">Если функция телефонной системы не включена в ваш план, возможно, потребуется приобрести лицензии на надстройки для **телефонной системы** .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="f7e4d-118">Необходимо также приобрести лицензии Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="f7e4d-119">Ознакомьтесь [со сведениями о лицензировании надстроек Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="f7e4d-120">[Назначение и удаление лицензий для Office 365 для бизнеса](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [лицензий "назначение Microsoft Teams](assign-teams-licenses.md)" и лицензий Exchange Online для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="f7e4d-121">Следуйте указаниям, соответствующим локальному решению по КОММУТИРУЕМой телефонной связи, развернутому для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="f7e4d-122">Для облачного соединителя Edition выполните инструкции в разделе **Включение пользователей для голосовой связи и служб голосовой почты** в [руководстве Настройка Skype для бизнеса Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="f7e4d-123">Для звонков по КОММУТИРУЕМой телефонной связи с помощью Skype для бизнеса Server [установите флажок включить локальные пользователи для предприятий](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="f7e4d-124">Для прямой маршрутизации в Teams настройте [прямую маршрутизацию](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail), следуя указаниям **Настройка номера телефона и включения корпоративной голосовой и голосовой почты** .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="f7e4d-p106">Транскрибирование голосовой почты поддерживается с марта 2017 г. и включено по умолчанию для всех организаций и пользователей. Отключить транскрибирование для организации можно с помощью Windows PowerShell и приведенных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="f7e4d-127">Сообщения голосовой почты доставляются в почтовый ящик Exchange пользователя по протоколу SMTP с помощью Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="f7e4d-128">Для успешной доставки этих сообщений убедитесь, что соединители Exchange настроены правильно между серверами Exchange и Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="f7e4d-129">[Настройка потока обработки почты с помощью соединителей](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="f7e4d-130">Для включения функций голосовой почты, таких как Настройка приветствий и визуальная голосовая почта в клиентах Skype для бизнеса, требуется подключение с Office 365 к почтовому ящику Exchange Server с помощью веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="f7e4d-131">Чтобы включить это подключение, необходимо настроить новый протокол проверки подлинности OAuth Exchange в разделе [Настройка проверки подлинности OAuth между организациями Exchange и Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx) .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="f7e4d-132">Мастер гибридной работы Exchange с Exchange 2013 CU5 или более поздней версии будет автоматически обрабатывать требования, описанные в действиях 5 и 6.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="f7e4d-133">Настройка политик голосовой почты в организации</span><span class="sxs-lookup"><span data-stu-id="f7e4d-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="f7e4d-134">Для пользователей Skype для бизнеса отключение голосовой почты с помощью политики вызова Microsoft Teams может также привести к отключению службы голосовой почты в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="f7e4d-135">Транскрибирование голосовой почты включено по умолчанию, a транскрибирование маскировки богохульства отключено по умолчанию для всех организаций и пользователей; тем не менее ими можно управлять с помощью командлетов [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) и [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="f7e4d-136">Сообщения голосовой почты, полученные от пользователей вашей организации, транскрибед в регионе, где размещается клиент Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-136">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="f7e4d-137">Область, в которой размещен ваш клиент, может не совпадать с регионом, в котором находится пользователь, получивший сообщение голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-137">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="f7e4d-138">Чтобы просмотреть область, в которой размещен ваш клиент, перейдите на страницу [профиля организации](https://go.microsoft.com/fwlink/p/?linkid=2067339) и нажмите кнопку **Просмотреть сведения** рядом с областью **данных**.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-138">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7e4d-139">Вы не можете создать новый экземпляр политики для транскрипции и ненормативной лексики с помощью командлета **New-ксонлиневоицемаилполици** , и вы не можете удалить существующий экземпляр политики с помощью командлета **Remove-ксонлиневоицемаилполици** . .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-139">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="f7e4d-140">Параметрами транскрибирования для пользователей можно управлять с помощью политик голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-140">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="f7e4d-141">Для просмотра всех доступных экземпляров политики голосовой почты можно использовать командлет [Get-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-141">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="f7e4d-142">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="f7e4d-142">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Результаты окна Get-CsOnlineVoiceMailPolicy.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="f7e4d-144">Выключение транскрибирования для организации</span><span class="sxs-lookup"><span data-stu-id="f7e4d-144">Turning off transcription for your organization</span></span>

<span data-ttu-id="f7e4d-p111">Так как по умолчанию для вашей организации транскрибирование включено, его можно отключить с помощью командлета [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="f7e4d-p111">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="f7e4d-147">Включение транскрибирования маскировки богохульства для вашей организации</span><span class="sxs-lookup"><span data-stu-id="f7e4d-147">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="f7e4d-148">Транскрибирования маскировки богохульства  отключено по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-148">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="f7e4d-149">Если для бизнеса требуется включение транскрибирования маскировки богохульства, его можно включить с помощью [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-149">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="f7e4d-150">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="f7e4d-150">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="f7e4d-151">Выключение транскрибирования для пользователя</span><span class="sxs-lookup"><span data-stu-id="f7e4d-151">Turning off transcription for a user</span></span>

<span data-ttu-id="f7e4d-152">Анализ политик пользователей выполняется до анализа параметров по умолчанию для организации.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-152">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="f7e4d-153">Например, если для всех пользователей включена транскрипция голосовой почты, вы можете назначить политике отключение транскрипции для определенного пользователя с помощью командлета [Grant-ксонлиневоицемаилполици](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f7e4d-153">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="f7e4d-154">Для отключения транскрибирования для одиночного пользователя выполните команду:</span><span class="sxs-lookup"><span data-stu-id="f7e4d-154">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="f7e4d-155">Включение транскрибирования маскировки богохульства для пользователя</span><span class="sxs-lookup"><span data-stu-id="f7e4d-155">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="f7e4d-156">Чтобы включить транскрибирование маскировки богохульства для определенного пользователя, можно назначить политики для включения транскрибирования маскировки богохульства для отдельного пользователя с помощью командлета [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7e4d-156">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="f7e4d-157">Чтобы включить транскрибирование маскировки богохульства для одного пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f7e4d-157">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="f7e4d-p114">Служба голосовой почты в Office 365 кэширует политики голосовой почты и обновляет кэш каждые 4 часа. Поэтому, процесс применения изменений, внесенных в политику, может выполняться до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-p114">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="f7e4d-160">Помощь пользователям в изучении возможностей голосовой почты Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f7e4d-160">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="f7e4d-p115">Мы предлагаем широкий выбор статей и учебных материалов, посвященных обучению пользователей работе с голосовой почтой Skype для бизнеса. Порекомендуйте пользователям следующие статьи.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="f7e4d-163">[Проверка сообщений и параметров голосовой почты в Skype для бизнеса](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8). В этой статье рассказывается о том, как прослушать сообщения голосовой почты в Skype для бизнеса, изменить параметры голосовой почты, а также прослушать сообщения с разной скоростью воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="f7e4d-163">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="f7e4d-164">Обучение работе со Skype для бизнеса 2016</span><span class="sxs-lookup"><span data-stu-id="f7e4d-164">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="f7e4d-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f7e4d-165">Related topics</span></span>
[<span data-ttu-id="f7e4d-166">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f7e4d-166">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="f7e4d-167">Возможности телефонной системы в Office 365</span><span class="sxs-lookup"><span data-stu-id="f7e4d-167">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f7e4d-168">Планирование миграции Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f7e4d-168">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


